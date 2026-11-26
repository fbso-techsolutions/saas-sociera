# ⚙️ TASK-0007 — Filtro de tenant (Hibernate @Filter)

| Campo | Valor |
|---|---|
| **Origem** | [US-FEAT-0002.0002-0003 — Tenant context](../../prj-produto/user-stories/US-FEAT-0002.0002-0003-tenant-context-filtro.md) |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | [Sprint 1](../../prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) |
| **Dono** | Thiago Daniel |
| **Esforço** | 8h |
| **Depende de** | [TASK-0005](TASK-0005-login-oidc.md) |

## 1. Objetivo

Derivar `tenant_id` do token e aplicar filtro automático em toda query.

## 2. O que implementar/entregar

- Resolução do tenant a partir do token JWT.
- `@FilterDef`/`@Filter` no Panache para as entidades multitenant.

## 3. Critério de saída

- [ ] Consulta de entidade retorna só dados do tenant do usuário autenticado.
