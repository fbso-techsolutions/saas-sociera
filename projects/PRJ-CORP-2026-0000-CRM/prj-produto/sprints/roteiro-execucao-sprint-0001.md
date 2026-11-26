# 🗺️ Roteiro de Execução — Sprint 1

> Ordem cronológica sugerida das tasks, respeitando as dependências do [board](board-sprint-0001.md).

| # | Task | Depende de | Dono | Janela |
|---|---|---|---|---|
| 1 | [TASK-0001 — Estrutura monorepo](../../prj-tecnico/tasks/TASK-0001-estrutura-monorepo.md) | — | Romeu Augusto | 07–08/12 |
| 2 | [TASK-0002 — docker-compose](../../prj-tecnico/tasks/TASK-0002-docker-compose.md) | [TASK-0001](../../prj-tecnico/tasks/TASK-0001-estrutura-monorepo.md) | Lourival Louro | 08–09/12 |
| 3 | [TASK-0003 — Workflow CI](../../prj-tecnico/tasks/TASK-0003-workflow-ci.md) | [TASK-0001](../../prj-tecnico/tasks/TASK-0001-estrutura-monorepo.md) | Romeu Augusto | 09–10/12 |
| 4 | [TASK-0004 — Realm + client Keycloak](../../prj-tecnico/tasks/TASK-0004-realm-client-keycloak.md) | [TASK-0002](../../prj-tecnico/tasks/TASK-0002-docker-compose.md) | Romeu Augusto | 10–11/12 |
| 5 | [TASK-0005 — Login OIDC](../../prj-tecnico/tasks/TASK-0005-login-oidc.md) | [TASK-0004](../../prj-tecnico/tasks/TASK-0004-realm-client-keycloak.md) | Thiago Daniel | 11–14/12 |
| 6 | [TASK-0006 — Proteção de rotas](../../prj-tecnico/tasks/TASK-0006-protecao-rotas.md) | [TASK-0005](../../prj-tecnico/tasks/TASK-0005-login-oidc.md) | Thiago Daniel | 14–15/12 |
| 7 | [TASK-0007 — Filtro tenant](../../prj-tecnico/tasks/TASK-0007-filter-tenant.md) | [TASK-0005](../../prj-tecnico/tasks/TASK-0005-login-oidc.md) | Thiago Daniel | 14–16/12 |
| 8 | [TASK-0008 — RLS](../../prj-tecnico/tasks/TASK-0008-rls.md) | [TASK-0007](../../prj-tecnico/tasks/TASK-0007-filter-tenant.md) | Thiago Daniel | 16–17/12 |
| 9 | [TASK-0009 — Teste isolamento](../../prj-tecnico/tasks/TASK-0009-teste-isolamento.md) | [TASK-0008](../../prj-tecnico/tasks/TASK-0008-rls.md) | Patricia Varra | 17–18/12 |

> **Review:** 18/12. **Retro:** 18/12 (após a review). Backend é o caminho crítico (Thiago, 26h);
> Felipe (frontend) apoia em testes/setup e na base React da [TASK-0001](../../prj-tecnico/tasks/TASK-0001-estrutura-monorepo.md).
