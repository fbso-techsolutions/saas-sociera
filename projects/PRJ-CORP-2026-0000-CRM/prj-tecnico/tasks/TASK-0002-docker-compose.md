# ⚙️ TASK-0002 — docker-compose (PostgreSQL + Keycloak)

| Campo | Valor |
|---|---|
| **Origem** | [ENABLER-0002 — Ambientes locais](../enablers/ENABLER-0002-ambientes-locais.md) |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | [Sprint 1](../../prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) |
| **Dono** | Lourival Louro |
| **Esforço** | 6h |
| **Depende de** | [TASK-0001](TASK-0001-estrutura-monorepo.md) |

## 1. Objetivo

Subir o ambiente local com PostgreSQL 17+ e Keycloak auto-hospedado.

## 2. O que implementar/entregar

- `docker-compose.yml` com PostgreSQL e Keycloak + healthcheck.
- Schema base (Flyway) e realm inicial de dev.

## 3. Critério de saída

- [ ] `docker compose up` sobe os dois serviços com healthcheck verde.
