# 🧭 EPIC-0012 — Eventos e Webhooks

| Campo | Valor |
|---|---|
| Projeto | FBSO CRM · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0012` — Eventos e Webhooks |
| B-REQs atendidas | B-REQ-09 |
| Features | 3 — `FEATURE-0012.0001` … `FEATURE-0012.0003` |
| Prioridade | Onda 3-Could (Fase 2) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** integrações precisam de eventos confiáveis, sem perda (dual-write) e com
  consumidores idempotentes.
- **Solução:** Transactional Outbox, contratos de eventos versionados (JSON tipado) e webhooks.
- **Impacto:** base resiliente para integrações com os SaaS — guardrail da org
  ([guardrail-eventos-outbox](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/architecture/guardrail-eventos-outbox.md)).

## 2. Fora do escopo

- Mensageria dedicada (Kafka/RabbitMQ) — só se justificar por volume (PENDENCY-0004).
- Integração vertical concreta (EPIC-0013).

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0012.0001` | Transactional Outbox | — (sem card) |
| `FEATURE-0012.0002` | Contratos de eventos versionados | — (sem card) |
| `FEATURE-0012.0003` | Webhooks de saída | — (sem card) |

## 4. Decisões pendentes

1. `[ ]` Nomenclatura de eventos consolidada (ex.: `lead.created`, `deal.stage_changed`).
