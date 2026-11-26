# 🧭 EPIC-0009 — Ingestão de Leads do Portal

| Campo | Valor |
|---|---|
| Projeto | Sociera · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0009` — Ingestão de Leads do Portal |
| B-REQs atendidas | B-REQ-06 |
| Features | 3 — `FEATURE-0009.0001` … `FEATURE-0009.0003` |
| Prioridade | Onda 1-Must (Fase 1) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** o portal captura leads, mas não há para onde fluírem — a integração
  [FEATURE-0006.0003](https://github.com/fbso-techsolutions/portal-fbso) fica travada.
- **Solução:** contrato de solução (OpenAPI + SDK + webhook) de ingestão de leads, com mapeamento
  de campos e origem de aquisição (`source`/`medium`/`campaign`).
- **Impacto:** desbloqueia a Release 2 do portal e inicia o funil comercial automaticamente.

## 2. Fora do escopo

- Outbound/marketing (fora do CRM).
- Enriquecimento de leads por IA (EPIC-0016 — evolução).

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0009.0001` | Contrato de solução (OpenAPI + SDK + webhook) | — (sem card) |
| `FEATURE-0009.0002` | Endpoint de ingestão de lead | — (sem card) |
| `FEATURE-0009.0003` | Mapeamento de campos + origem de aquisição | — (sem card) |

## 4. Decisões pendentes

1. `[ ]` Schema do lead (campos 1:1 com o formulário do portal) — com PM/PO + Comercial.
2. `[ ]` Idempotência e retry (guardrail de eventos) — no desenho do contrato.
