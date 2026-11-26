# ⚙️ TASK-0006 — Proteção de rotas (401)

| Campo | Valor |
|---|---|
| **Origem** | [US-FEAT-0002.0001-0002 — Auth OIDC](../../prj-produto/user-stories/US-FEAT-0002.0001-0002-autenticacao-oidc-backend.md) |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | [Sprint 1](../../prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) |
| **Dono** | Thiago Daniel |
| **Esforço** | 4h |
| **Depende de** | [TASK-0005](TASK-0005-login-oidc.md) |

## 1. Objetivo

Proteger as rotas de API contra acesso não autenticado.

## 2. O que implementar/entregar

- Config de segurança: rotas protegidas por padrão, healthcheck liberado.

## 3. Critério de saída

- [ ] Requisição sem token → 401; com token válido → 200.
