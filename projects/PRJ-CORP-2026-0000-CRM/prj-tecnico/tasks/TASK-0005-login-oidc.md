# ⚙️ TASK-0005 — Login OIDC no backend

| Campo | Valor |
|---|---|
| **Origem** | [US-FEAT-0002.0001-0002 — Auth OIDC](../../prj-produto/user-stories/US-FEAT-0002.0001-0002-autenticacao-oidc-backend.md) |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | [Sprint 1](../../prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) |
| **Dono** | Thiago Daniel |
| **Esforço** | 8h |
| **Depende de** | [TASK-0004](TASK-0004-realm-client-keycloak.md) |

## 1. Objetivo

Integrar a dependência OIDC no backend e validar o token JWT nas requisições.

## 2. O que implementar/entregar

- Dependência OIDC (Quarkus) + endpoint de login/issuer.
- Validação de assinatura/expiração do JWT.

## 3. Critério de saída

- [ ] Token válido → 200; sem token → 401.
