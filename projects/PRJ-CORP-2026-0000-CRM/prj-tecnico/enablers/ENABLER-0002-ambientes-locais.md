# 🔧 ENABLER-0002 — Ambientes locais (docker-compose)

| Campo | Valor |
|---|---|
| **Categoria** | Infraestrutura |
| **Origem** | [EPIC-0001 — Fundação e Engenharia](../../prj-produto/epicos/EPIC-0001-fundacao-engenharia.md) (Fase 0) |
| **Habilita** | [FEATURE-0002.0001](../../prj-produto/features/FEATURE-0002.0001-autenticacao-oidc.md) (auth) · [FEATURE-0002.0004](../../prj-produto/features/FEATURE-0002.0004-segregacao-multi-tenant.md) (RLS) |
| **Depende de** | ENABLER-0001 (estrutura) |
| **Dono sugerido** | Lourival Louro (Infra) |
| **Estimativa (Job Size)** | 3 |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Visão Geral e Contexto

- **Categoria:** Infraestrutura.
- **Origem:** EPIC-0001.
- **Status de Bloqueio:** Habilitador de cadência — o dev local depende de PostgreSQL + Keycloak
  subindo juntos.

## 2. Análise de Priorização (WSJF)

- **Valor de Negócio:** remove fricção de setup do time.
- **Habilitação de Oportunidade:** base do MVP em Docker Compose (alvo SaaS = K8s/Helm).

## 3. Escopo Técnico Detalhado

1. Criar `docker-compose.yml` com PostgreSQL 17+ e Keycloak auto-hospedado.
2. Subir schema base (Flyway) e realm inicial de dev.
3. Documentar o fluxo `up`/`down`/reset.

> **Não** inclui: CI (ENABLER-0003) nem deploy.

## 4. Critérios de Saída (DoD)

- [ ] `docker compose up` sobe PostgreSQL + Keycloak sem erro, com healthcheck verde.
- [ ] Backend conecta no PostgreSQL local e autentica no Keycloak local.
