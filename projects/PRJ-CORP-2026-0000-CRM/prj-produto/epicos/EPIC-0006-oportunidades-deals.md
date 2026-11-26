# 🧭 EPIC-0006 — Gestão de Oportunidades (Deals)

| Campo | Valor |
|---|---|
| Projeto | Sociera · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0006` — Gestão de Oportunidades (Deals) |
| B-REQs atendidas | B-REQ-04 |
| Features | 3 — `FEATURE-0006.0001` … `FEATURE-0006.0003` |
| Prioridade | Onda 1-Must (Fase 1) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** sem registrar oportunidades com etapa, valor e responsável, o funil não é
  operacionalizável no dia a dia.
- **Solução:** CRUD de `Deal` vinculado a Party + Pipeline, com Kanban e valores/moeda.
- **Impacto:** acompanhamento real das oportunidades (propostas de consultoria/engenharia).

## 2. Fora do escopo

- Previsão/forecast e automação de ganho (evolução — eventos).
- Integração com pagamento (fora do CRM).

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0006.0001` | CRUD de Oportunidades (Deal) | — (sem card) |
| `FEATURE-0006.0002` | Kanban de oportunidades | — (sem card) |
| `FEATURE-0006.0003` | Valor, moeda e metadata | — (sem card) |

## 4. Decisões pendentes

1. `[ ]` Campos obrigatórios mínimos do Deal (responsável, próxima atividade).
2. ✅ Histórico de movimentação de etapa: `deal_stage_history` (tempo em cada fase) — [ADR-003](../../../../docs/tecnico/arquitetura/adrs/adr-003-pipeline-stages-relacional.md).
