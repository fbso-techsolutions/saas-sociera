# 🔌 Integração — Ingestão de Leads (portal → Sociera)

| Campo | Valor |
|---|---|
| **Responde** | FEATURE-0009.0001 (contrato de solução) — [card](../../../../projects/PRJ-CORP-2026-0000-CRM/prj-produto/features/FEATURE-0009.0001-contrato-solucao-lead.md) |
| **Requisitos** | B-REQ-06 (receber leads do portal automaticamente) |
| **Decisão** | [ADR-001 (estratégia de integrações)](https://github.com/fbso-techsolutions/platform-standards/blob/main/governance/adrs/adr-001-estrategia-integracoes.md) — contrato de solução (OpenAPI + SDK + webhook) · [ADR-004 (ACL + Outbox)](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/architecture/guardrail-eventos-outbox.md) |
| **Contrato** | [openapi-ingestao-leads.yaml](contratos/openapi-ingestao-leads.yaml) |
| **Dono** | Eng (Thiago Daniel) + PM/PO (Marcela Bianco) |
| **Consumido por** | [portal-fbso FEATURE-0006.0003](https://github.com/fbso-techsolutions/portal-fbso) (envio de leads) |
| **Status** | 📝 **PROPOSTA (0.3.0)** — modelagem (offerings/contact/category/status), escopo CRUD e segurança decididos (§7); URL base/escopos a confirmar |

## 1. Objetivo e escopo (CRUD — domínio de Leads)

- **Ingestão (`POST /v1/leads`):** o portal envia um lead e o Sociera o persiste como Party
  (role `LEAD`) com origem de aquisição e evidência de privacidade (LGPD). Idempotente via
  `Idempotency-Key`.
- **Consulta (`GET /v1/leads` e `/v1/leads/{leadId}`):** listagem e detalhe para o CRM interno.

## 2. Visão da integração

```mermaid
flowchart LR
    subgraph PORTAL["portal-fbso (consumidor)"]
        FORM["Formulário\n(contato/interesse/consultoria)"]
        W["Worker/API\n(FEATURE-0006.0002)"]
    end
    subgraph SOCIERA["Sociera (monólito modular)"]
        API["POST /v1/leads"]
        PORT["LeadIngestionPort\n(porta)"]
        AD["LeadIngestionAdapter\n(ACL — ADR-004)"]
        OUT["Outbox"]
    end
    FORM --> W -->|"envia lead + Idempotency-Key"| API
    API --> PORT --> AD --> OUT
    AD -->|"persiste Party (role LEAD)"| OUT
```

## 3. Componentes (ACL)

```mermaid
classDiagram
    class LeadIngestionPort {
        <<interface>>
        +ingest(tenantId, LeadCreate, idempotencyKey) LeadCreated
    }
    class LeadIngestionAdapter {
        +ingest(tenantId, LeadCreate, idempotencyKey) LeadCreated
    }
    class LeadMapper {
        +toParty(dto) Party
    }
    class LeadDeduplicator {
        +findByKey(key) Lead?
        +findByEmail(tenantId, email) Lead?
    }
    class OutboxPublisher

    LeadIngestionPort <|.. LeadIngestionAdapter
    LeadIngestionAdapter --> LeadMapper
    LeadIngestionAdapter --> LeadDeduplicator
    LeadIngestionAdapter --> OutboxPublisher
```

## 4. Fluxo — ingestão de lead

```mermaid
sequenceDiagram
    participant P as portal-fbso
    participant API as POST /v1/leads
    participant AD as LeadIngestionAdapter
    participant OUT as Outbox
    P->>API: POST /v1/leads + Idempotency-Key
    API->>AD: ingest(tenantId, dto, key)
    AD->>AD: dedup por key/email
    alt novo lead
        AD->>OUT: persiste Party(LEAD) + evento lead.created
        OUT-->>P: 201 {id, status:NEW}
    else duplicado
        OUT-->>P: 409 {id, status:DUPLICATED}
    end
```

## 5. Contrato

- **`POST /v1/leads`** (`ingestLead`) — corpo `LeadIngestionRequest` (`contact` + `interest` +
  `privacy` obrigatórios; `organization`/`message`/`acquisition` opcionais) + header
  `Idempotency-Key` (obrigatório) e `X-Correlation-ID` (opcional).
- **`GET /v1/leads`** (`listLeads`) — listagem com filtros (`status`/`category`/`email`) e paginação.
- **`GET /v1/leads/{leadId}`** (`getLead`) — detalhe.
- **Idempotência (distinta da dedup):** mesma chave + mesmo conteúdo → **200** (replay, header
  `Idempotency-Replayed`) · mesma chave + conteúdo diferente → **409** · primeira vez → **201**.
- **Dedup:** email por tenant → associa à Party existente (status `ASSOCIATED`); telefone
  normalizado E.164 (não é chave isolada).
- **Multi-tenancy:** `tenant_id` das **claims do token JWT** (Keycloak) — nunca de header/parâmetro.
- **Erros:** RFC 9457 (`application/problem+json`).
- **Evento de saída:** `lead.created` (versionado).

## 6. Resiliência e erros

| Situação | Resposta |
|---|---|
| Reenvio com mesma `Idempotency-Key` (retry) | **200** com o lead original (não duplica) |
| Nova chave + email já existente no tenant | **409** `DUPLICATED` (dedup) |
| Consentimento `false`/sem evidência (version/timestamp) | 400 (LGPD) |
| Sociera indisponível | portal registra pendência + retry |
| Falha no processamento | Outbox reentrega (at-least-once, consumidor idempotente) |

**Dedup:** chave primária = `email` por tenant; telefone normalizado em E.164 (não é chave de
dedup isolada no MVP — evita falso-positivo de leads que compartilham número).

## 7. Pendências de fechamento

1. ✅ **Modelagem (P3–P6)** — catálogo unificado `offerings` (SaaS + consultoria) · `contact`
   sempre pessoa (INDIVIDUAL) + `organization` = empresa B2B · `category` só macro
   (`SAAS`/`CONSULTING`/`PARTNERSHIP`/`OTHER`) · `status` = `NEW`/`ASSOCIATED`.
2. ✅ **Escopo (P7)** — API CRUD: `POST` (ingestão) + `GET` (listar/detalhar).
3. ✅ **Segurança (P1)** — `http bearer` (sem `tokenUrl`); client credentials documentado na descrição.
4. `[ ]` **URL base + escopos definitivos** — com o Arquiteto (Ricardo David) e Infra (Lourival Louro).

## 8. Rastreabilidade

| Elemento | ADR/Regra | Onde vive |
|---|---|---|
| `LeadIngestionPort` (ACL) | ADR-001 · ADR-004 | §3 |
| Idempotência (`Idempotency-Key` + dedup) | ADR-004 (Outbox/idempotência) | §5, §6 |
| Evento `lead.created` (versionado) | guardrail-eventos-outbox | §5 |
| Consentimento LGPD obrigatório | PENDENCY-0019 (portal) | §5 (campo `consent`) |
