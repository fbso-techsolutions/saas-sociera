# 📝 PRD Ágil — Projeto PRJ-CORP-2026-0000-CRM (Fase 0/1 — MVP)

> Versão: 0.1 (rascunho) | Status: 📝 Em formação
>
> Este PRD cobre o **escopo do projeto**. A **visão do produto** vive em
> [docs/negocio/visao.md](../../docs/negocio/visao.md).

## 1. Objetivo do projeto

Criar a **Sociera** — CRM próprio (simples) da FBSO Technology Solutions — SaaS multi-tenant — começando
pelo núcleo de relacionamento (Party/Roles), funil comercial (Pipeline/Deals), tarefas/interações,
auditoria e **ingestão de leads do portal** (desbloqueia `portal-fbso` FEATURE-0006.0003). A
primeira validação é a operação comercial da **FBSO Tech Services** (dogfooding).

## 2. Requisitos de negócio (B-REQ)

> Fonte canônica: [prj-negocio/requisitos/requisitos-negocio.md](prj-negocio/requisitos/requisitos-negocio.md).

| B-REQ | Necessidade | Prioridade | Fase |
|---|---|---|---|
| B-REQ-01 | Operar isolado por organização (multi-tenant) com identidade e acesso controlado | Must | 1 |
| B-REQ-02 | Cadastrar e organizar pessoas e organizações (Party) | Must | 1 |
| B-REQ-03 | Atribuir papéis e registrar relacionamentos | Must | 1 |
| B-REQ-04 | Gerir funil comercial e oportunidades (pipeline + deals) | Must | 1 |
| B-REQ-05 | Registrar tarefas e interações do relacionamento | Must | 1 |
| B-REQ-06 | Receber leads do portal automaticamente | Must | 1 |
| B-REQ-07 | Auditar operações relevantes | Must | 1 |
| B-REQ-08 | Atender clientes via tickets e SLAs | Should | 2 |
| B-REQ-09 | Integrar com os SaaS da FBSO (APIs + eventos) | Should | 3 |
| B-REQ-10 | Orquestrar processos com Kestra | Could | 3 |
| B-REQ-11 | Evoluir para oferta SaaS B2B comercializável (templates/IA) | Could | Pós-tração |

## 3. Mapeamento de Épicos

> Árvore completa em [prj-produto/rastreabilidade.md](prj-produto/rastreabilidade.md).
> **Legado → novo** (plano `EP-xx` → org `EPIC-{NNNN}`): `EP-01→EPIC-0001 … EP-08→EPIC-0008`;
> `EPIC-0009` = **novo** (ingestão de leads); `EP-09→EPIC-0010 … EP-15→EPIC-0016`.

| Épico | B-REQ | Onda | Fase |
|---|---|---|---|
| [EPIC-0001 — Fundação e Engenharia](prj-produto/epicos/EPIC-0001-fundacao-engenharia.md) | — (enabler) | 1-Must | 0 |
| [EPIC-0002 — Identidade e Multi-tenancy](prj-produto/epicos/EPIC-0002-identidade-multi-tenancy.md) | B-REQ-01 | 1-Must | 1 |
| [EPIC-0003 — Cadastro de Parties](prj-produto/epicos/EPIC-0003-cadastro-parties.md) | B-REQ-02 | 1-Must | 1 |
| [EPIC-0004 — Papéis e Relacionamentos](prj-produto/epicos/EPIC-0004-papeis-relacionamentos.md) | B-REQ-03 | 2-Should | 1 |
| [EPIC-0005 — Pipeline Comercial](prj-produto/epicos/EPIC-0005-pipeline-comercial.md) | B-REQ-04 | 1-Must | 1 |
| [EPIC-0006 — Gestão de Oportunidades (Deals)](prj-produto/epicos/EPIC-0006-oportunidades-deals.md) | B-REQ-04 | 1-Must | 1 |
| [EPIC-0007 — Atividades e Interações](prj-produto/epicos/EPIC-0007-atividades-interacoes.md) | B-REQ-05 | 2-Should | 1 |
| [EPIC-0008 — Auditoria](prj-produto/epicos/EPIC-0008-auditoria.md) | B-REQ-07 | 1-Must | 1 |
| [EPIC-0009 — Ingestão de Leads do Portal](prj-produto/epicos/EPIC-0009-ingestao-leads-portal.md) | B-REQ-06 | 1-Must | 1 |
| [EPIC-0010 — Atendimento (Tickets)](prj-produto/epicos/EPIC-0010-atendimento-tickets.md) | B-REQ-08 | 3-Could | 2 |
| [EPIC-0011 — SLA e Base de Conhecimento](prj-produto/epicos/EPIC-0011-sla-base-conhecimento.md) | B-REQ-08 | 3-Could | 2 |
| [EPIC-0012 — Eventos e Webhooks](prj-produto/epicos/EPIC-0012-eventos-webhooks.md) | B-REQ-09 | 3-Could | 2 |
| [EPIC-0013 — Integração Vertical (primeiro SaaS)](prj-produto/epicos/EPIC-0013-integracao-vertical.md) | B-REQ-09 | 3-Could | 3 |
| [EPIC-0014 — Orquestração Kestra](prj-produto/epicos/EPIC-0014-orquestracao-kestra.md) | B-REQ-10 | 3-Could | 3 |
| [EPIC-0015 — Extensões de Domínio](prj-produto/epicos/EPIC-0015-extensoes-dominio.md) | B-REQ-11 | Pós-tração | — |
| [EPIC-0016 — IA aplicada ao CRM](prj-produto/epicos/EPIC-0016-ia-aplicada.md) | B-REQ-11 | Pós-tração | — |

## 4. Estrutura de Engenharia

> Stack e guardrails: [docs/tecnico/arquitetura/README.md](../../docs/tecnico/arquitetura/README.md) ·
> [AGENTS.md §5](../../AGENTS.md) — Java 25 + Quarkus · PostgreSQL 17+ (RLS) · Flyway · React/TS (web) ·
> Keycloak auto-hospedado. Guardrails corporativos:
> [platform-standards/standards/architecture/](https://github.com/fbso-techsolutions/platform-standards/tree/main/standards/architecture).

## 5. Frentes (cross-repo)

| Frente | Repo | Contrato | Status |
|---|---|---|---|
| Ingestão de leads do portal → CRM | [portal-fbso](https://github.com/fbso-techsolutions/portal-fbso) (FEATURE-0006.0003) ↔ [saas-crm](https://github.com/fbso-techsolutions/saas-crm) | OpenAPI + SDK + webhook (ACL) | 📝 a definir |

> Segue o [ADR-002 (projeto transversal)](https://github.com/fbso-techsolutions/platform-standards/blob/main/governance/adrs/adr-002-projeto-transversal.md):
> o portal é o **lar**; esta frente é a integração controlada pelo contrato de solução.

## 6. Mapa de documentos

| Frente | Documento | Caminho |
|---|---|---|
| Produto | Visão | [docs/negocio/visao.md](../../docs/negocio/visao.md) |
| Produto | Capacidades | [docs/produto/README.md](../../docs/produto/README.md) |
| Produto | Domínio (Party Model) | [docs/tecnico/domain.md](../../docs/tecnico/domain.md) |
| Produto | Arquitetura | [docs/tecnico/arquitetura/README.md](../../docs/tecnico/arquitetura/README.md) |
| Projeto | Demanda de origem | [prj-negocio/discovery/PEDIDO.md](prj-negocio/discovery/PEDIDO.md) |
| Projeto | Requisitos (B-REQ) | [prj-negocio/requisitos/requisitos-negocio.md](prj-negocio/requisitos/requisitos-negocio.md) |
| Projeto | Épicos + rastreabilidade | [prj-produto/](prj-produto) |
| Projeto | Enablers e runways | [prj-tecnico/](prj-tecnico) |
| Projeto | Hub de pendências | [pendencias.md](pendencias.md) |
| Projeto | Equipe | [equipe.md](equipe.md) |
| Processo | Padrões ágeis | [platform-standards/standards/agile/](https://github.com/fbso-techsolutions/platform-standards/tree/main/standards/agile) |

## 7. Decisões pendentes deste documento

1. ✅ **ID do projeto** — `PRJ-CORP-2026-0000-CRM` (área `CORP`) definido.
2. ✅ **Stack** — Java 25 · PostgreSQL 17+ · Keycloak · Flyway ([ADR-001](../../docs/tecnico/arquitetura/adrs/adr-001-stack-crm.md)); sugestões de Java 21/PG 16 **rejeitadas**.
3. ✅ **Multi-tenancy** (duas camadas) — [ADR-002](../../docs/tecnico/arquitetura/adrs/adr-002-multi-tenant-duas-camadas.md).
4. ✅ **Etapas de pipeline** (tabela relacional) — [ADR-003](../../docs/tecnico/arquitetura/adrs/adr-003-pipeline-stages-relacional.md).
5. ✅ **Mensageria MVP** (Outbox + scheduler + webhook, sem broker) — [ADR-004](../../docs/tecnico/arquitetura/adrs/adr-004-mensageria-outbox-scheduler.md).
6. `[ ]` **Nome de marca** do CRM — [PENDENCY-0001](pendencias.md).
7. `[ ]` **Domínio próprio** — [PENDENCY-0002](pendencias.md).
8. `[ ]` **Kestra** (componente novo de plataforma) — [PENDENCY-0003](pendencias.md).
9. `[ ]` **Time/squad** do CRM — [PENDENCY-0006](pendencias.md).
