# ADR-001 - Stack do FBSO CRM (Java 25 · PostgreSQL 17+ · Keycloak · Flyway)

| Campo | Conteúdo |
|---|---|
| **Data / Status** | 2026-11-26 · ✅ **Decidida** (proposta do PO; assinaturas a coletar — PENDENCY-0006) |
| **Contexto** | O plano de implementação (`.temporaria/ideias/crm/`) e a sugestão `0001` deixaram a stack em aberto (Java "21 ou 25", PostgreSQL "16+", "Keycloak ou Auth0"). A org já padronizou a stack nos demais SaaS (`saas-materiae`) e em `platform-standards`. |
| **Decisão** | Adotar a stack da org, **sem reabrir**: **Java 25** + Quarkus (Mandrel) · **PostgreSQL 17+** (RLS) · **Flyway** · React + TypeScript (web) · **Keycloak auto-hospedado**. |
| **Justificativa** | Consistência com `saas-materiae` e `platform-standards`; Java 25 já é o padrão da org (não há ganho em regredir para 21); PostgreSQL 17+ com RLS atende o isolamento multi-tenant; Flyway é o padrão de migração; Keycloak auto-hospedado evita custo por usuário (MAU) ao escalar. |
| **Consequências** | Fase 0/1 seguem a stack da org; sem bifurcação de runtime/migração/identidade entre produtos. |
| **Alternativas rejeitadas** | **Java 21 LTS** (sugestão 0001): regressão ao padrão da org; **PostgreSQL 16** (sugestão 0001): abaixo do padrão org; **Auth0**: custo por MAU e divergência do Keycloak auto-hospedado. |
| **Rastreio** | [AGENTS.md §5](../../../../AGENTS.md) · [arquitetura](../README.md) · `platform-standards/standards/architecture/` |
| **Assinatura** | — (a assinar — squad a preencher, PENDENCY-0006) |
