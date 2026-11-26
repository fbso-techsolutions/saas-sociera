# ⚙️ TASK-0004 — Realm + client Keycloak (config como código)

| Campo | Valor |
|---|---|
| **Origem** | [US-FEAT-0002.0001-0001 — Realm + client](../../prj-produto/user-stories/US-FEAT-0002.0001-0001-realm-client-keycloak.md) |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | [Sprint 1](../../prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) |
| **Dono** | Romeu Augusto |
| **Esforço** | 6h |
| **Depende de** | [TASK-0002](TASK-0002-docker-compose.md) |

## 1. Objetivo

Provisionar realm e client do Keycloak de forma versionada (config como código).

## 2. O que implementar/entregar

- Script/export do realm (realm + client + issuer).
- Aplicação reproduzível no ambiente local.

## 3. Critério de saída

- [ ] Realm/client recriados idênticos após `down` + reapply.
