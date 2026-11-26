# 🔌 Integração — Ingestão de Leads (portal → Sociera)

| Campo | Valor |
|---|---|
| **Responde** | FEATURE-0009.0001 (contrato de solução) — [card](../../../../projects/PRJ-CORP-2026-0000-CRM/prj-produto/features/FEATURE-0009.0001-contrato-solucao-lead.md) |
| **Requisitos** | B-REQ-06 (receber leads do portal automaticamente) |
| **Decisão** | [ADR-001 (estratégia de integrações)](https://github.com/fbso-techsolutions/platform-standards/blob/main/governance/adrs/adr-001-estrategia-integracoes.md) — contrato de solução (OpenAPI + SDK + webhook) · [ADR-004 (ACL + Outbox)](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/architecture/guardrail-eventos-outbox.md) |
| **Contrato** | [openapi-ingestao-leads.yaml](contratos/openapi-ingestao-leads.yaml) |
| **Dono** | Eng (Thiago Daniel) + PM/PO (Marcela Bianco) |
| **Consumido por** | [portal-fbso FEATURE-0006.0003](https://github.com/fbso-techsolutions/portal-fbso) (envio de leads) |
| **Status** | 📝 **PROPOSTA** — fechamento do contrato com PM/PO + Comercial pendente (§7) |

## 1. Objetivo e escopo (integração unidirecional)

- **Entrada (síncrona/assíncrona):** o portal envia um lead (`POST /v1/leads`) e o Sociera o
  persiste como Party (role `LEAD`) com origem de aquisição (`source`/`medium`/`campaign`) e
  consentimento LGPD. Idempotente via `Idempotency-Key` (dedup de reenvio).

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

- **`POST /v1/leads`** com header **`Idempotency-Key`** (obrigatório) e corpo `LeadCreate`
  (`name`, `email`, `interest`, `consent` obrigatórios; `phone`, `company`, `message`,
  `source`/`medium`/`campaign` opcionais).
- **201** lead criado · **202** aceito assíncrono · **400** validação/consentimento ausente ·
  **401** token inválido · **409** duplicado · **503** indisponível.
- **Evento de saída:** `lead.created` (versionado) — alimenta auditoria e futuras integrações.

## 6. Resiliência e erros

| Situação | Resposta |
|---|---|
| Reenvio com mesma `Idempotency-Key` | 409 `DUPLICATED` (não duplica) |
| Email já existente no tenant | 409 `DUPLICATED` (dedup) |
| Consentimento `false`/ausente | 400 (LGPD) |
| Sociera indisponível | portal registra pendência + retry |
| Falha no processamento | Outbox reentrega (at-least-once, consumidor idempotente) |

## 7. Pendências de fechamento (PM/PO + Comercial)

1. **Campos exatos do lead** — 1:1 com o formulário do portal (FEATURE-0009.0001 §8).
2. **Valores canônicos de `interest`** — catálogo final (Educatio/Fiscalia/Mercator/Materiae/Sociera/Consultoria).
3. **URL base + escopos OAuth2** (client credentials) — com o Arquiteto (Ricardo David).

## 8. Rastreabilidade

| Elemento | ADR/Regra | Onde vive |
|---|---|---|
| `LeadIngestionPort` (ACL) | ADR-001 · ADR-004 | §3 |
| Idempotência (`Idempotency-Key` + dedup) | ADR-004 (Outbox/idempotência) | §5, §6 |
| Evento `lead.created` (versionado) | guardrail-eventos-outbox | §5 |
| Consentimento LGPD obrigatório | PENDENCY-0019 (portal) | §5 (campo `consent`) |
