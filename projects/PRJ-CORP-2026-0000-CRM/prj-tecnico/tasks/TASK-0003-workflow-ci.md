# ⚙️ TASK-0003 — Workflow CI (GitHub Actions)

| Campo | Valor |
|---|---|
| **Origem** | [ENABLER-0003 — CI](../enablers/ENABLER-0003-ci-github-actions.md) |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | [Sprint 1](../../prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) |
| **Dono** | Romeu Augusto |
| **Esforço** | 4h |
| **Depende de** | [TASK-0001](TASK-0001-estrutura-monorepo.md) |

## 1. Objetivo

Criar o workflow de CI no PR (build/testes backend + lint/typecheck/test frontend), reusando a platform-standards.

## 2. O que implementar/entregar

- Workflow `.github/workflows/` com `uses:` da platform-standards.
- Status check configurado para bloquear merge.

## 3. Critério de saída

- [ ] PR aberto dispara CI; código quebrado falha o check.
