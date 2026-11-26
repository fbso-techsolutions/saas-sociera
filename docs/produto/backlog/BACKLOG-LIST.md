# 🗄️ Backlog — Fila única do produto (Sociera)

> **Fonte única de todo o trabalho** do Sociera. Colunas e régua `Check`/`Status`:
> [guia de gestão de projetos](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/agile/guia-gestao-projetos.md).

## 1. Em execução / pronto (Sprint 1)

| Check | Projeto | Feature | Tipo | ID | Título | Est. | Dono | Entregue por | Depende de | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| 👷 | PRJ-CORP-2026-0000-CRM | EPIC-0001 | Enabler | ENABLER-0001 | [Repositório e estrutura monorepo](../prj-tecnico/enablers/ENABLER-0001-repositorio-estrutura.md) | 3 | Romeu Augusto | Sprint 1 | — | ⬜ |
| 👷 | PRJ-CORP-2026-0000-CRM | EPIC-0001 | Enabler | ENABLER-0002 | [Ambientes locais](../prj-tecnico/enablers/ENABLER-0002-ambientes-locais.md) | 3 | Lourival Louro | Sprint 1 | ENABLER-0001 | ⬜ |
| 👷 | PRJ-CORP-2026-0000-CRM | EPIC-0001 | Enabler | ENABLER-0003 | [CI (GitHub Actions)](../prj-tecnico/enablers/ENABLER-0003-ci-github-actions.md) | 2 | Romeu Augusto | Sprint 1 | ENABLER-0001 | ⬜ |
| 👷 | PRJ-CORP-2026-0000-CRM | FEATURE-0002.0001 | User Story | US-FEAT-0002.0001-0001 | [Realm + client Keycloak](../prj-produto/user-stories/US-FEAT-0002.0001-0001-realm-client-keycloak.md) | 3 | Romeu Augusto | Sprint 1 | ENABLER-0002 | ✅ Revisado |
| 👷 | PRJ-CORP-2026-0000-CRM | FEATURE-0002.0001 | User Story | US-FEAT-0002.0001-0002 | [Auth OIDC backend](../prj-produto/user-stories/US-FEAT-0002.0001-0002-autenticacao-oidc-backend.md) | 5 | Thiago Daniel | Sprint 1 | US-0002.0001-0001 | ✅ Revisado |
| 👷 | PRJ-CORP-2026-0000-CRM | FEATURE-0002.0002 | User Story | US-FEAT-0002.0002-0003 | [Tenant context (Hibernate @Filter)](../prj-produto/user-stories/US-FEAT-0002.0002-0003-tenant-context-filtro.md) | 5 | Thiago Daniel | Sprint 1 | US-0002.0001-0002 | ✅ Revisado |
| 👷 | PRJ-CORP-2026-0000-CRM | FEATURE-0002.0004 | User Story | US-FEAT-0002.0004-0004 | [RLS + teste de isolamento](../prj-produto/user-stories/US-FEAT-0002.0004-0004-rls-isolamento.md) | 5 | Thiago Daniel | Sprint 1 | US-0002.0002-0003 | ✅ Revisado |

## 2. Features (backlog de produto)

| Check | Projeto | Feature | Tipo | ID | Título | Est. | Depende de | Status |
|---|---|---|---|---|---|---|---|---|
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0002.0001 | [Autenticação OIDC](../prj-produto/features/FEATURE-0002.0001-autenticacao-oidc.md) | — | ENABLER-0002 | ✅ Revisado |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0002.0002 | [Contexto de tenant](../prj-produto/features/FEATURE-0002.0002-contexto-tenant.md) | — | 0002.0001 | ✅ Revisado |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0002.0003 | [RBAC](../prj-produto/features/FEATURE-0002.0003-rbac.md) | — | 0002.0001 | 📝 Rascunho |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0002.0004 | [Segregação multi-tenant](../prj-produto/features/FEATURE-0002.0004-segregacao-multi-tenant.md) | — | 0002.0002 | ✅ Revisado |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0009.0001 | [Contrato de solução](../prj-produto/features/FEATURE-0009.0001-contrato-solucao-lead.md) | — | 0002.0001 | 📝 Rascunho |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0009.0002 | [Endpoint de ingestão](../prj-produto/features/FEATURE-0009.0002-endpoint-ingestao-lead.md) | — | 0009.0001 | 📝 Rascunho |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0009.0003 | [Mapeamento campos/origem](../prj-produto/features/FEATURE-0009.0003-mapeamento-campos-origem.md) | — | 0009.0002 | 📝 Rascunho |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0003.0001 | Cadastro de Parties (PF/PJ) | — | 0002.0004 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0003.0002 | Busca e filtros | — | 0003.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0003.0003 | Atributos customizados (JSONB) | — | 0003.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0004.0001 | Papéis de Party (PartyRole) | — | 0003.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0004.0002 | Relacionamentos | — | 0004.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0005.0001 | Pipelines configuráveis | — | 0003.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0005.0002 | Etapas e histórico | — | 0005.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0006.0001 | CRUD de Oportunidades | — | 0005.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0006.0002 | Kanban | — | 0006.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0006.0003 | Valor, moeda e metadata | — | 0006.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0007.0001 | Tarefas | — | 0003.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0007.0002 | Interações | — | 0007.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0007.0003 | Histórico | — | 0007.0001 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0008.0001 | Audit Log imutável | — | 0002.0002 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0010.0001 | Filas de atendimento | — | Fase 2 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0010.0002 | Tickets | — | Fase 2 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0010.0003 | Histórico de atendimento | — | Fase 2 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0011.0001 | Regras de SLA | — | Fase 2 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0011.0002 | Escalonamento | — | Fase 2 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0011.0003 | Base de conhecimento | — | Fase 2 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0012.0001 | Transactional Outbox | — | Fase 2 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0012.0002 | Contratos de eventos | — | Fase 2 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0012.0003 | Webhooks | — | Fase 2 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0013.0001 | Seleção SaaS + contrato | — | Fase 3 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0013.0002 | Sync de clientes | — | Fase 3 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0013.0003 | Oportunidades automáticas | — | Fase 3 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0014.0001 | Fluxos onboarding (Kestra) | — | Fase 3 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0014.0002 | Fluxos SLA (Kestra) | — | Fase 3 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0014.0003 | Fluxos cross-SaaS (Kestra) | — | Fase 3 | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0015.0001 | Templates de indústria | — | Pós-tração | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0015.0002 | Configurações por vertical | — | Pós-tração | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0016.0001 | Qualificação de leads (IA) | — | Pós-tração | a criar |
| 💡 | PRJ-CORP-2026-0000-CRM | — | Feature | FEATURE-0016.0002 | Resumo/enriquecimento (IA) | — | Pós-tração | a criar |
