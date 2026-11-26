# 🗂️ Board — Sprint 1 (Fundação e Multi-tenancy) · 07/12/2026 – 18/12/2026

> **O que é:** camada fina de status da Sprint 1 — 7 itens (3 enablers + 4 stories). Camada grossa: [backlog](../../../../docs/produto/backlog/BACKLOG-LIST.md). Estados: `Backlog priorizado` → `Em Dev` → `Em Review` → `Em Testes` → `Concluído`.

| Campo | Valor |
|---|---|
| **Sprint** | 07/12 – 18/12/2026 · 10 dias úteis |
| **Escopo** | 4 stories + 3 enablers |
| **WIP `Em Dev`** | 2 / limite |
| **Atualizado** | 26/11/2026 |

## Itens

| Check | Item | Estado | Dono | Depende de | Tasks | Próxima ação | Evidência |
|---|---|---|---|---|---|---|---|
| 💡 | [ENABLER-0001 — Repositório e estrutura](../prj-tecnico/enablers/ENABLER-0001-repositorio-estrutura.md) | `Backlog priorizado` | Romeu Augusto | — | [TASK-0001](../prj-tecnico/tasks/TASK-0001-estrutura-monorepo.md) | iniciar 07/12 | — |
| 💡 | [ENABLER-0002 — Ambientes locais](../prj-tecnico/enablers/ENABLER-0002-ambientes-locais.md) | `Backlog priorizado` | Lourival Louro | ENABLER-0001 | [TASK-0002](../prj-tecnico/tasks/TASK-0002-docker-compose.md) | após TASK-0001 | — |
| 💡 | [ENABLER-0003 — CI](../prj-tecnico/enablers/ENABLER-0003-ci-github-actions.md) | `Backlog priorizado` | Romeu Augusto | ENABLER-0001 | [TASK-0003](../prj-tecnico/tasks/TASK-0003-workflow-ci.md) | após TASK-0001 | — |
| 💡 | [US-0002.0001-0001 — Realm Keycloak](../prj-produto/user-stories/US-FEAT-0002.0001-0001-realm-client-keycloak.md) | `Backlog priorizado` | Romeu Augusto | ENABLER-0002 | [TASK-0004](../prj-tecnico/tasks/TASK-0004-realm-client-keycloak.md) | após TASK-0002 | — |
| 💡 | [US-0002.0001-0002 — Auth OIDC](../prj-produto/user-stories/US-FEAT-0002.0001-0002-autenticacao-oidc-backend.md) | `Backlog priorizado` | Thiago Daniel | US-0002.0001-0001 | [TASK-0005](../prj-tecnico/tasks/TASK-0005-login-oidc.md) · [TASK-0006](../prj-tecnico/tasks/TASK-0006-protecao-rotas.md) | após US-0001 | — |
| 💡 | [US-0002.0002-0003 — Tenant context](../prj-produto/user-stories/US-FEAT-0002.0002-0003-tenant-context-filtro.md) | `Backlog priorizado` | Thiago Daniel | US-0002.0001-0002 | [TASK-0007](../prj-tecnico/tasks/TASK-0007-filter-tenant.md) | após US-0002 | — |
| 💡 | [US-0002.0004-0004 — RLS + isolamento](../prj-produto/user-stories/US-FEAT-0002.0004-0004-rls-isolamento.md) | `Backlog priorizado` | Thiago Daniel | US-0002.0002-0003 | [TASK-0008](../prj-tecnico/tasks/TASK-0008-rls.md) · [TASK-0009](../prj-tecnico/tasks/TASK-0009-teste-isolamento.md) | após US-0003 | — |

**Resumo:** `Concluído` 0 · `Em Dev` 0 · `Em Review` 0 · `Em Testes` 0 · bloqueados 0.

**Compromisso da sprint:** 18 SP (stories) · 8 Job Size (enablers).

## Tasks (saída do Planning)

| Check | Task | Origem | Status | Esforço (h) | Dono |
|---|---|---|---|---|---|
| 💡 | TASK-0001 — Estrutura monorepo | ENABLER-0001 | `Planejada` | 4 | Romeu Augusto |
| 💡 | TASK-0002 — docker-compose | ENABLER-0002 | `Planejada` | 6 | Lourival Louro |
| 💡 | TASK-0003 — Workflow CI | ENABLER-0003 | `Planejada` | 4 | Romeu Augusto |
| 💡 | TASK-0004 — Realm + client | US-0002.0001-0001 | `Planejada` | 6 | Romeu Augusto |
| 💡 | TASK-0005 — Login OIDC | US-0002.0001-0002 | `Planejada` | 8 | Thiago Daniel |
| 💡 | TASK-0006 — Proteção de rotas | US-0002.0001-0002 | `Planejada` | 4 | Thiago Daniel |
| 💡 | TASK-0007 — Filtro tenant | US-0002.0002-0003 | `Planejada` | 8 | Thiago Daniel |
| 💡 | TASK-0008 — RLS | US-0002.0004-0004 | `Planejada` | 6 | Thiago Daniel |
| 💡 | TASK-0009 — Teste isolamento | US-0002.0004-0004 | `Planejada` | 4 | Patricia Varra |

**Total de esforço:** 50h.

## Capacidade

| Recurso | Papel | Horas comprometidas | Disponibilidade | Saldo |
|---|---|---|---|---|
| Thiago Daniel | Dev backend | 26 | 80 | +54 |
| Romeu Augusto | Tech Lead | 14 | 80 | +66 |
| Lourival Louro | Infra | 6 | 20 | +14 |
| Patricia Varra | QA | 4 | 20 | +16 |
