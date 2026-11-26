# 🧭 EPIC-0002 — Identidade e Multi-tenancy

| Campo | Valor |
|---|---|
| Projeto | FBSO CRM · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0002` — Identidade e Multi-tenancy |
| B-REQs atendidas | B-REQ-01 |
| Features | 4 — `FEATURE-0002.0001` … `FEATURE-0002.0004` |
| Prioridade | Onda 1-Must (Fase 1) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** sem isolamento por organização e controle de acesso, não há como oferecer o CRM
  como SaaS nem proteger dados de clientes.
- **Solução:** autenticação OIDC (Keycloak auto-hospedado), contexto de tenant derivado do usuário
  autenticado, RBAC e testes de segregação.
- **Impacto:** base de segurança e confiança — pré-requisito de qualquer entrega de dados.

## 2. Fora do escopo

- SSO unificado com os demais SaaS (Release 3 do portal — fora deste épico).
- Self-service de onboarding de tenants (Fase 4).

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0002.0001` | Autenticação OIDC (Keycloak) | — (sem card) |
| `FEATURE-0002.0002` | Contexto de tenant (contexto autenticado) | — (sem card) |
| `FEATURE-0002.0003` | RBAC (usuários, papéis, permissões) | — (sem card) |
| `FEATURE-0002.0004` | Segregação e testes entre tenants | — (sem card) |

## 4. Decisões pendentes

1. ✅ Isolamento em **duas camadas**: Hibernate `@Filter` (aplicação) + RLS `SET LOCAL app.current_tenant` (banco) — [ADR-002](../../../../docs/tecnico/arquitetura/adrs/adr-002-multi-tenant-duas-camadas.md).
