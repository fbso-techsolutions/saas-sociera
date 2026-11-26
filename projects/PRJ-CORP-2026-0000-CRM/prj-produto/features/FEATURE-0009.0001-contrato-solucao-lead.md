# ✨ FEATURE-0009.0001 — Contrato de solução (ingestão de leads)

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Épico** | [EPIC-0009 — Ingestão de Leads do Portal](../epicos/EPIC-0009-ingestao-leads-portal.md) |
| **B-REQ dona** | B-REQ-06 |
| **Prioridade** | Onda 1-Must (MVP) |
| **Requisitos** | B-REQ-06 |
| **Depende de** | FEATURE-0002.0001 (auth OIDC) |
| **Entra depois** | FEATURE-0009.0002 (endpoint) |
| **User stories** | — (a criar — Sprint 2) |
| **🔒 Travada por** | — (livre) |
| **Status** | 📝 Rascunho (2026-11-26) |

## 1. Objetivo de negócio

Definir o contrato de solução (OpenAPI + SDK + webhook) de ingestão de leads, desbloqueando a
Release 2 do `portal-fbso` (FEATURE-0006.0003).

## 2. Escopo

### Entra
- Contrato OpenAPI do recurso de ingestão de lead — [openapi-ingestao-leads.yaml](../../../../docs/tecnico/arquitetura/integracoes/contratos/openapi-ingestao-leads.yaml) + [doc de integração](../../../../docs/tecnico/arquitetura/integracoes/integracao-ingestao-leads.md).
- Schema do lead (contato, produto/interesse, origem `source`/`medium`/`campaign`).

### Frentes (cross-repo)

| Escopo Cross | Repo | Status |
|---|---|---|
| Portal → Sociera: envio de lead | [portal-fbso](https://github.com/fbso-techsolutions/portal-fbso) (FEATURE-0006.0003) | a iniciar |

### Fora (nesta feature)
- Endpoint de ingestão implementado → FEATURE-0009.0002.
- Outbound/marketing → fora do CRM.

## 7. Critérios de aceite da feature (DoD)

- [ ] Contrato OpenAPI publicado com schema 1:1 com o formulário do portal.

## 8. Decisões pendentes deste documento

1. `[ ]` Campos exatos do lead — com PM/PO (Marcela Bianco) + Comercial (Ursula Companero).
