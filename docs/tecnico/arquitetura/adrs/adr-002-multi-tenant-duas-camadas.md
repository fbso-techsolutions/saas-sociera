# ADR-002 - Multi-tenancy em duas camadas (Hibernate + RLS)

| Campo | Conteúdo |
|---|---|
| **Data / Status** | 2026-11-26 · ✅ **Decidida** |
| **Contexto** | Isolamento entre tenants é requisito de segurança e arquitetura (meta "incidente zero" de vazamento). Filtro só na aplicação deixa query nativa desprotegida; RLS só no banco não cobre a injeção do contexto. |
| **Decisão** | Isolar em **duas camadas**: (1) **aplicação** — filtro automático do Hibernate (`@FilterDef`/`@Filter` no Panache) injetando `tenant_id` do token JWT em toda query; (2) **banco** — Row-Level Security via `SET LOCAL app.current_tenant = '<uuid>'` na conexão transacional, bloqueando acessos que escapem o filtro. |
| **Justificativa** | Defesa em profundidade: se um desenvolvedor esquecer um filtro em query nativa, o banco ainda bloqueia; se o contexto não for definido, o banco nega acesso (fail-closed). |
| **Consequências** | Testes de tentativa de acesso entre tenants obrigatórios; contexto de tenant sempre derivado do token autenticado (nunca `tenant_id` enviado pelo cliente); política de RLS e papel de banco da aplicação detalhados antes do MVP. |
| **Alternativas rejeitadas** | **Só `tenant_id` + filtros na aplicação**: query nativa sem filtro vaza; **só RLS**: não resolve a origem do contexto nem a conveniência de escrita; **schema por tenant**: custo operacional alto e dificulta evolução/migração. |
| **Rastreio** | [arquitetura §4](../README.md) · [domain.md](../../domain.md) · `platform-standards/standards/architecture/guardrail-multi-tenant.md` |
| **Assinatura** | Tech lead (Romeu Augusto) + Arquiteto de Soluções (Ricardo David) · 2026-11-26 |
