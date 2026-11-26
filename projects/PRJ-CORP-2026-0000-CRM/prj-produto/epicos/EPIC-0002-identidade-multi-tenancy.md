# 🧭 EPIC-0002 — Identidade e Multi-tenancy

| Campo | Valor |
|---|---|
| Projeto | Sociera · PRJ-CORP-2026-0000-CRM |
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
| [FEATURE-0002.0001 — Autenticação OIDC](../features/FEATURE-0002.0001-autenticacao-oidc.md) | Autenticação OIDC (Keycloak) | [US-0001](../user-stories/US-FEAT-0002.0001-0001-realm-client-keycloak.md) · [US-0002](../user-stories/US-FEAT-0002.0001-0002-autenticacao-oidc-backend.md) |
| [FEATURE-0002.0002 — Contexto de tenant](../features/FEATURE-0002.0002-contexto-tenant.md) | Contexto de tenant | [US-0003](../user-stories/US-FEAT-0002.0002-0003-tenant-context-filtro.md) |
| [FEATURE-0002.0003 — RBAC](../features/FEATURE-0002.0003-rbac.md) | RBAC (usuários, papéis, permissões) | — (a criar) |
| [FEATURE-0002.0004 — Segregação](../features/FEATURE-0002.0004-segregacao-multi-tenant.md) | Segregação e testes entre tenants | [US-0004](../user-stories/US-FEAT-0002.0004-0004-rls-isolamento.md) |

## 4. Decisões pendentes

1. ✅ Isolamento em **duas camadas**: Hibernate `@Filter` (aplicação) + RLS `SET LOCAL app.current_tenant` (banco) — [ADR-002](../../../../docs/tecnico/arquitetura/adrs/adr-002-multi-tenant-duas-camadas.md).
