# ⚙️ TASK-0008 — RLS (Row-Level Security)

| Campo | Valor |
|---|---|
| **Origem** | [US-FEAT-0002.0004-0004 — RLS + isolamento](../../prj-produto/user-stories/US-FEAT-0002.0004-0004-rls-isolamento.md) |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | [Sprint 1](../../prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) |
| **Dono** | Thiago Daniel |
| **Esforço** | 6h |
| **Depende de** | [TASK-0007](TASK-0007-filter-tenant.md) |

## 1. Objetivo

Aplicar Row-Level Security no PostgreSQL (segunda camada de isolamento).

## 2. O que implementar/entregar

- Migração Flyway com políticas RLS por tenant.
- `SET LOCAL app.current_tenant` na conexão transacional.

## 3. Critério de saída

- [ ] Query sem `app.current_tenant` definido é negada (fail-closed).
