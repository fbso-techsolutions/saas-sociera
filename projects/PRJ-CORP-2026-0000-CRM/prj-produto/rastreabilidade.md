# 🔗 Matriz de Rastreabilidade — Sociera

> **O que é:** fonte única da cadeia **B-REQ → Épico → Feature → Story → Sprint → Task →
> Release/Build/Deploy** (e vice-versa). **Aponta, não copia:** cada célula é um ID/link; a
> especificação mora no documento do item.

## Régua do `Check`

| Check | Estado | Critério |
|---|---|---|
| 🚩 | Não-iniciado | requisito **sem épico** (nada definido) |
| 💡 | Em documentação | tem épico/feature/story, **sem sprint** (execução não definida) |
| 👷 | Em implementação | tem sprint, **não entregue** |
| 🏁 | Concluído | **entregue** (DoD + produção) |
| 🚫 | Cancelado | **desconsiderado** |

## Régua do `Compliance` (alinhamento vertical)

| Valor | Significado |
|---|---|
| 🟢 | alinhado — o filho está conforme o objetivo/escopo do pai |
| 🟡 | desvio a revisar — parcialmente alinhado |
| 🔴 | desalinhado — fora do escopo/objetivo do pai, **ou órfão** (sem pai) |
| `—` | a julgar (PO no refinamento) |

> Julgamento **humano (semântico)** — régua completa:
> [guia](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/agile/guia-matriz-rastreabilidade.md).

## 1. Cadeia de valor — requisito → entrega

| Check | Requisito | Épico | Feature | Produto/Serviço | Story | Sprint | Task | Release | Compliance |
|---|---|---|---|---|---|---|---|---|---|
| 👷 | B-REQ-01 | [EPIC-0002 — Identidade e Multi-tenancy](epicos/EPIC-0002-identidade-multi-tenancy.md) | [FEATURE-0002.0001 — Autenticação OIDC](features/FEATURE-0002.0001-autenticacao-oidc.md) | [saas-sociera](../../../README.md) | [US-0002.0001-0001 — Realm+client](user-stories/US-FEAT-0002.0001-0001-realm-client-keycloak.md) | [Sprint 1](sprints/sprint-0001-fundacao-multi-tenancy.md) | [TASK-0004](../prj-tecnico/tasks/TASK-0004-realm-client-keycloak.md) | — | — |
| 👷 | B-REQ-01 | [EPIC-0002](epicos/EPIC-0002-identidade-multi-tenancy.md) | [FEATURE-0002.0001 — Autenticação OIDC](features/FEATURE-0002.0001-autenticacao-oidc.md) | [saas-sociera](../../../README.md) | [US-0002.0001-0002 — Auth backend](user-stories/US-FEAT-0002.0001-0002-autenticacao-oidc-backend.md) | [Sprint 1](sprints/sprint-0001-fundacao-multi-tenancy.md) | [TASK-0005](../prj-tecnico/tasks/TASK-0005-login-oidc.md) · [TASK-0006](../prj-tecnico/tasks/TASK-0006-protecao-rotas.md) | — | — |
| 👷 | B-REQ-01 | [EPIC-0002](epicos/EPIC-0002-identidade-multi-tenancy.md) | [FEATURE-0002.0002 — Contexto de tenant](features/FEATURE-0002.0002-contexto-tenant.md) | [saas-sociera](../../../README.md) | [US-0002.0002-0003 — Filtro tenant](user-stories/US-FEAT-0002.0002-0003-tenant-context-filtro.md) | [Sprint 1](sprints/sprint-0001-fundacao-multi-tenancy.md) | [TASK-0007](../prj-tecnico/tasks/TASK-0007-filter-tenant.md) | — | — |
| 👷 | B-REQ-01 | [EPIC-0002](epicos/EPIC-0002-identidade-multi-tenancy.md) | [FEATURE-0002.0004 — Segregação](features/FEATURE-0002.0004-segregacao-multi-tenant.md) | [saas-sociera](../../../README.md) | [US-0002.0004-0004 — RLS+isolamento](user-stories/US-FEAT-0002.0004-0004-rls-isolamento.md) | [Sprint 1](sprints/sprint-0001-fundacao-multi-tenancy.md) | [TASK-0008](../prj-tecnico/tasks/TASK-0008-rls.md) · [TASK-0009](../prj-tecnico/tasks/TASK-0009-teste-isolamento.md) | — | — |
| 💡 | B-REQ-01 | [EPIC-0002](epicos/EPIC-0002-identidade-multi-tenancy.md) | [FEATURE-0002.0003 — RBAC](features/FEATURE-0002.0003-rbac.md) | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 👷 | — (enabler) | [EPIC-0001 — Fundação](epicos/EPIC-0001-fundacao-engenharia.md) | — | [saas-sociera](../../../README.md) | [ENABLER-0001 — Repositório](../prj-tecnico/enablers/ENABLER-0001-repositorio-estrutura.md) | [Sprint 1](sprints/sprint-0001-fundacao-multi-tenancy.md) | [TASK-0001](../prj-tecnico/tasks/TASK-0001-estrutura-monorepo.md) | — | — |
| 👷 | — (enabler) | [EPIC-0001 — Fundação](epicos/EPIC-0001-fundacao-engenharia.md) | — | [saas-sociera](../../../README.md) | [ENABLER-0002 — Ambientes](../prj-tecnico/enablers/ENABLER-0002-ambientes-locais.md) | [Sprint 1](sprints/sprint-0001-fundacao-multi-tenancy.md) | [TASK-0002](../prj-tecnico/tasks/TASK-0002-docker-compose.md) | — | — |
| 👷 | — (enabler) | [EPIC-0001 — Fundação](epicos/EPIC-0001-fundacao-engenharia.md) | — | [saas-sociera](../../../README.md) | [ENABLER-0003 — CI](../prj-tecnico/enablers/ENABLER-0003-ci-github-actions.md) | [Sprint 1](sprints/sprint-0001-fundacao-multi-tenancy.md) | [TASK-0003](../prj-tecnico/tasks/TASK-0003-workflow-ci.md) | — | — |
| 💡 | B-REQ-06 | [EPIC-0009 — Ingestão de Leads](epicos/EPIC-0009-ingestao-leads-portal.md) | [FEATURE-0009.0001 — Contrato](features/FEATURE-0009.0001-contrato-solucao-lead.md) | [saas-sociera](../../../README.md) | — (a criar — Sprint 2) | — | — | — | — |
| 💡 | B-REQ-06 | [EPIC-0009](epicos/EPIC-0009-ingestao-leads-portal.md) | [FEATURE-0009.0002 — Endpoint](features/FEATURE-0009.0002-endpoint-ingestao-lead.md) | [saas-sociera](../../../README.md) | — (a criar — Sprint 2) | — | — | — | — |
| 💡 | B-REQ-06 | [EPIC-0009](epicos/EPIC-0009-ingestao-leads-portal.md) | [FEATURE-0009.0003 — Mapeamento](features/FEATURE-0009.0003-mapeamento-campos-origem.md) | [saas-sociera](../../../README.md) | — (a criar — Sprint 2) | — | — | — | — |
| 💡 | B-REQ-02 | [EPIC-0003 — Cadastro de Parties](epicos/EPIC-0003-cadastro-parties.md) | `FEATURE-0003.0001…0003.0003` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-03 | [EPIC-0004 — Papéis e Relacionamentos](epicos/EPIC-0004-papeis-relacionamentos.md) | `FEATURE-0004.0001 · 0004.0002` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-04 | [EPIC-0005 — Pipeline Comercial](epicos/EPIC-0005-pipeline-comercial.md) | `FEATURE-0005.0001 · 0005.0002` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-04 | [EPIC-0006 — Gestão de Oportunidades (Deals)](epicos/EPIC-0006-oportunidades-deals.md) | `FEATURE-0006.0001…0006.0003` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-05 | [EPIC-0007 — Atividades e Interações](epicos/EPIC-0007-atividades-interacoes.md) | `FEATURE-0007.0001…0007.0003` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-07 | [EPIC-0008 — Auditoria](epicos/EPIC-0008-auditoria.md) | `FEATURE-0008.0001` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-08 | [EPIC-0010 — Atendimento (Tickets)](epicos/EPIC-0010-atendimento-tickets.md) | `FEATURE-0010.0001…0010.0003` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-08 | [EPIC-0011 — SLA e Base de Conhecimento](epicos/EPIC-0011-sla-base-conhecimento.md) | `FEATURE-0011.0001…0011.0003` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-09 | [EPIC-0012 — Eventos e Webhooks](epicos/EPIC-0012-eventos-webhooks.md) | `FEATURE-0012.0001…0012.0003` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-09 | [EPIC-0013 — Integração Vertical](epicos/EPIC-0013-integracao-vertical.md) | `FEATURE-0013.0001…0013.0003` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-10 | [EPIC-0014 — Orquestração Kestra](epicos/EPIC-0014-orquestracao-kestra.md) | `FEATURE-0014.0001…0014.0003` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-11 | [EPIC-0015 — Extensões de Domínio](epicos/EPIC-0015-extensoes-dominio.md) | `FEATURE-0015.0001 · 0015.0002` | [saas-sociera](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-11 | [EPIC-0016 — IA aplicada ao CRM](epicos/EPIC-0016-ia-aplicada.md) | `FEATURE-0016.0001 · 0016.0002` | [saas-sociera](../../../README.md) | — | — | — | — | — |

> **Legado → novo:** `EP-01→EPIC-0001 … EP-08→EPIC-0008`; `EPIC-0009` = novo (ingestão de leads);
> `EP-09→EPIC-0010 … EP-15→EPIC-0016`.
