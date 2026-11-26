# 🧭 EPIC-0005 — Pipeline Comercial

| Campo | Valor |
|---|---|
| Projeto | Sociera · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0005` — Pipeline Comercial |
| B-REQs atendidas | B-REQ-04 |
| Features | 2 — `FEATURE-0005.0001` · `FEATURE-0005.0002` |
| Prioridade | Onda 1-Must (Fase 1) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** o comercial precisa de funis com etapas próprias por tipo de venda (consultoria,
  produtos).
- **Solução:** pipelines configuráveis por tenant, com etapas ordenadas e histórico de transições.
- **Impacto:** processo de vendas padronizado e auditável.

## 2. Fora do escopo

- Automações de movimentação de etapa (evolução — eventos/Kestra).
- Dashboards/relatórios (evolução).

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0005.0001` | Pipelines configuráveis | — (sem card) |
| `FEATURE-0005.0002` | Etapas e histórico de transições | — (sem card) |

## 4. Decisões pendentes

1. ✅ Etapas em **tabela própria** (`pipeline_stages` + `deal_stage_history`) — não JSONB — [ADR-003](../../../../docs/tecnico/arquitetura/adrs/adr-003-pipeline-stages-relacional.md).
