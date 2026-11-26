# ✨ FEATURE-0009.0002 — Endpoint de ingestão de lead

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Épico** | [EPIC-0009 — Ingestão de Leads do Portal](../epicos/EPIC-0009-ingestao-leads-portal.md) |
| **B-REQ dona** | B-REQ-06 |
| **Prioridade** | Onda 1-Must (MVP) |
| **Requisitos** | B-REQ-06 |
| **Depende de** | FEATURE-0009.0001 (contrato) |
| **Entra depois** | FEATURE-0009.0003 (mapeamento) |
| **User stories** | — (a criar — Sprint 2) |
| **🔒 Travada por** | — (livre) |
| **Status** | 📝 Rascunho (2026-11-26) |

## 1. Objetivo de negócio

Receber leads do portal via API/webhook e persistir como Party (role LEAD), com idempotência e
retry (guardrail de eventos).

## 2. Escopo

### Entra
- Endpoint de ingestão de lead (webhook/API).
- Idempotência e tratamento de falha (não perde lead).

### Fora (nesta feature)
- Mapeamento de campos/origem → FEATURE-0009.0003.
- Enriquecimento por IA → EPIC-0016.

## 7. Critérios de aceite da feature (DoD)

- [ ] Lead enviado é persistido e retorna 201/202 idempotente.

## 8. Decisões pendentes deste documento

1. `[ ]` Idempotência por chave (lead dedup) — no desenho do contrato.
