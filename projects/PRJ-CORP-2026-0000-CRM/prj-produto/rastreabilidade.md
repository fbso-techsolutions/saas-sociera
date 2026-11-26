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
| 💡 | B-REQ-01 | [EPIC-0002 — Identidade e Multi-tenancy](epicos/EPIC-0002-identidade-multi-tenancy.md) | `FEATURE-0002.0001…0002.0004` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-02 | [EPIC-0003 — Cadastro de Parties](epicos/EPIC-0003-cadastro-parties.md) | `FEATURE-0003.0001…0003.0003` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-03 | [EPIC-0004 — Papéis e Relacionamentos](epicos/EPIC-0004-papeis-relacionamentos.md) | `FEATURE-0004.0001 · 0004.0002` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-04 | [EPIC-0005 — Pipeline Comercial](epicos/EPIC-0005-pipeline-comercial.md) | `FEATURE-0005.0001 · 0005.0002` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-04 | [EPIC-0006 — Gestão de Oportunidades (Deals)](epicos/EPIC-0006-oportunidades-deals.md) | `FEATURE-0006.0001…0006.0003` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-05 | [EPIC-0007 — Atividades e Interações](epicos/EPIC-0007-atividades-interacoes.md) | `FEATURE-0007.0001…0007.0003` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-06 | [EPIC-0009 — Ingestão de Leads do Portal](epicos/EPIC-0009-ingestao-leads-portal.md) | `FEATURE-0009.0001…0009.0003` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-07 | [EPIC-0008 — Auditoria](epicos/EPIC-0008-auditoria.md) | `FEATURE-0008.0001` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | — (enabler) | [EPIC-0001 — Fundação e Engenharia](epicos/EPIC-0001-fundacao-engenharia.md) | `FEATURE-0001.0001…0001.0004` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-08 | [EPIC-0010 — Atendimento (Tickets)](epicos/EPIC-0010-atendimento-tickets.md) | `FEATURE-0010.0001…0010.0003` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-08 | [EPIC-0011 — SLA e Base de Conhecimento](epicos/EPIC-0011-sla-base-conhecimento.md) | `FEATURE-0011.0001…0011.0003` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-09 | [EPIC-0012 — Eventos e Webhooks](epicos/EPIC-0012-eventos-webhooks.md) | `FEATURE-0012.0001…0012.0003` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-09 | [EPIC-0013 — Integração Vertical (primeiro SaaS)](epicos/EPIC-0013-integracao-vertical.md) | `FEATURE-0013.0001…0013.0003` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-10 | [EPIC-0014 — Orquestração Kestra](epicos/EPIC-0014-orquestracao-kestra.md) | `FEATURE-0014.0001…0014.0003` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-11 | [EPIC-0015 — Extensões de Domínio](epicos/EPIC-0015-extensoes-dominio.md) | `FEATURE-0015.0001 · 0015.0002` | [saas-crm](../../../README.md) | — | — | — | — | — |
| 💡 | B-REQ-11 | [EPIC-0016 — IA aplicada ao CRM](epicos/EPIC-0016-ia-aplicada.md) | `FEATURE-0016.0001 · 0016.0002` | [saas-crm](../../../README.md) | — | — | — | — | — |

> **Legado → novo:** `EP-01→EPIC-0001 … EP-08→EPIC-0008`; `EPIC-0009` = novo (ingestão de leads);
> `EP-09→EPIC-0010 … EP-15→EPIC-0016` (plano `.temporaria/ideias/crm/`).
