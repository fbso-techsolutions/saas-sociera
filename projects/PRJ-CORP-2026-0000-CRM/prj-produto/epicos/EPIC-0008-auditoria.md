# 🧭 EPIC-0008 — Auditoria

| Campo | Valor |
|---|---|
| Projeto | FBSO CRM · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0008` — Auditoria |
| B-REQs atendidas | B-REQ-07 |
| Features | 1 — `FEATURE-0008.0001` |
| Prioridade | Onda 1-Must (Fase 1) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** operações relevantes (mudança de etapa, alteração de cadastro) precisam ser
  rastreáveis e imutáveis para governança e LGPD.
- **Solução:** registro de auditoria com `ator_id`, imutável, vinculado ao tenant.
- **Impacto:** trilha de auditoria como fonte de confiança e conformidade.

## 2. Fora do escopo

- Retenção/anonimização automática (política — evolui com LGPD).
- Dashboards de auditoria (evolução).

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0008.0001` | Audit Log imutável | — (sem card) |

## 4. Decisões pendentes

1. `[ ]` Política de retenção/exclusão de dados pessoais (LGPD) — com jurídico.
