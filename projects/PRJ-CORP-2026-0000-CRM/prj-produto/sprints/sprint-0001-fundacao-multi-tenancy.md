# 🗓️ Sprint 1 — Fundação e Multi-tenancy · 07/12/2026 – 18/12/2026

> **Status:** `Planejada` · **Sprint Goal:** "Estabelecer a fundação do Sociera (repo, ambientes, CI) com autenticação OIDC e isolamento multi-tenant em duas camadas." · **Board:** [board-sprint-0001.md](board-sprint-0001.md) · **Verdade única do corte:** este documento

| Campo | Valor |
|---|---|
| **Empresa / Marca** | Sociera by FBSO |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | Sprint 1 — Fundação e Multi-tenancy |
| **Período** | 07/12 (seg) → 18/12 (sex) · **2 semanas** (10 dias úteis) |
| **Sprint Goal** | Fundação (repo, ambientes, CI) + autenticação OIDC + isolamento multi-tenant em duas camadas |
| **Foco** | enablers de fundação (Fase 0) + stories de multi-tenancy (MVP) |
| **Capacidade** | ver §3 |
| **Escopo** | ver §2 — 3 enablers + 4 stories |
| **Documentos-âncora** | [backlog](../../../../docs/produto/backlog/BACKLOG-LIST.md) · [board](board-sprint-0001.md) · [DoR](checklist-dor-sprint-0001.md) |
| **Dono do documento** | Tech lead (Romeu Augusto) + PM/PO (Marcela Bianco) |

## 1. Sprint Goal

### 1.1 Objetivo

Subir a base de engenharia (monorepo, ambientes locais, CI) e fechar a primeira camada do
multi-tenancy — autenticação OIDC (Keycloak) e isolamento em duas camadas (Hibernate + RLS).

### 1.2 Valor de negócio

Sem fundação e isolamento multi-tenant, nenhuma entrega de dados (Parties, Deals) é segura nem
operável. Esta sprint destrava todo o restante do MVP.

### 1.3 Resultados esperados

- [ ] Monorepo com base Quarkus + React compilando e com CI verde.
- [ ] Ambiente local sobe (PostgreSQL + Keycloak) com autenticação OIDC funcional.
- [ ] Isolamento multi-tenant em duas camadas com teste de cross-tenant provando "incidente zero".

## 2. Escopo da Sprint (o corte)

### 2.1 Itens comprometidos

| Item | SP/JS | Tipo | Tasks | Depende de | 🔒 Travada por |
|---|---|---|---|---|---|
| [ENABLER-0001 — Repositório e estrutura monorepo](../prj-tecnico/enablers/ENABLER-0001-repositorio-estrutura.md) | 3 | 🔧 Enabler | [TASK-0001](../prj-tecnico/tasks/TASK-0001-estrutura-monorepo.md) | — | — |
| [ENABLER-0002 — Ambientes locais](../prj-tecnico/enablers/ENABLER-0002-ambientes-locais.md) | 3 | 🔧 Enabler | [TASK-0002](../prj-tecnico/tasks/TASK-0002-docker-compose.md) | ENABLER-0001 | — |
| [ENABLER-0003 — CI](../prj-tecnico/enablers/ENABLER-0003-ci-github-actions.md) | 2 | 🔧 Enabler | [TASK-0003](../prj-tecnico/tasks/TASK-0003-workflow-ci.md) | ENABLER-0001 | — |
| [US-FEAT-0002.0001-0001 — Realm + client Keycloak](../prj-produto/user-stories/US-FEAT-0002.0001-0001-realm-client-keycloak.md) | 3 | 💬 Story | [TASK-0004](../prj-tecnico/tasks/TASK-0004-realm-client-keycloak.md) | ENABLER-0002 | — |
| [US-FEAT-0002.0001-0002 — Auth OIDC backend](../prj-produto/user-stories/US-FEAT-0002.0001-0002-autenticacao-oidc-backend.md) | 5 | 💬 Story | [TASK-0005](../prj-tecnico/tasks/TASK-0005-login-oidc.md) · [TASK-0006](../prj-tecnico/tasks/TASK-0006-protecao-rotas.md) | US-0002.0001-0001 | — |
| [US-FEAT-0002.0002-0003 — Tenant context](../prj-produto/user-stories/US-FEAT-0002.0002-0003-tenant-context-filtro.md) | 5 | 💬 Story | [TASK-0007](../prj-tecnico/tasks/TASK-0007-filter-tenant.md) | US-0002.0001-0002 | — |
| [US-FEAT-0002.0004-0004 — RLS + isolamento](../prj-produto/user-stories/US-FEAT-0002.0004-0004-rls-isolamento.md) | 5 | 💬 Story | [TASK-0008](../prj-tecnico/tasks/TASK-0008-rls.md) · [TASK-0009](../prj-tecnico/tasks/TASK-0009-teste-isolamento.md) | US-0002.0002-0003 | — |
| **Total** | **18 SP + 8 JS** | | | | |

### 2.2 Itens não incluídos

- FEATURE-0009.0001/0002 (contrato + endpoint de ingestão de leads): depende do backend autenticado — Sprint 2.
- FEATURE-0003.0001 (cadastro de Parties): primeiro cadastro real — Sprint 2.
- FEATURE-0002.0003 (RBAC): refinamento de papéis — Sprint 2.

### 2.3 Premissas e restrições

**Premissas:** Keycloak auto-hospedado disponível via docker; Node/Java nas versões da org (Java 25, Node 24). **Restrições:** sem deploy (ambiente local apenas); Kestra/mobile fora do MVP.

## 3. Capacidade e estimativas

### 3.1 Capacidade da equipe

| Papel / Pessoa | Disponibilidade bruta (sprint) | Observação |
|---|---|---|
| Dev backend (Thiago Daniel) | 80 h | — |
| Dev frontend (Felipe Luiz) | 80 h | sem stories frontend — apoio em testes/setup |
| Infra (Lourival Louro) | 20 h | 25% |
| QA (Patricia Varra) | 20 h | 25% (teste de isolamento) |

### 3.2 Alocação por tipo (capacity allocation — guia §4.1)

| Fatia | % | Volume |
|---|---|---|
| Valor de negócio (stories) | ~70% | 18 SP |
| Enablers / infraestrutura | ~20% | 8 JS |
| Débito técnico + bugs | ~10% | 0 |

## 4. Riscos, dependências e travas

### 4.1 Riscos

| ID | Risco | Impacto | Probabilidade | Mitigação | Responsável |
|---|---|---|---|---|---|
| RISK-0001 | Keycloak não subir de forma reprodutível | Alto | Média | config como código (realm versionado) | Lourival Louro |

### 4.2 Dependências e bloqueios

— (nenhum bloqueio externo no início; registrar `BLOCKER-{NNNN}` no [hub](../pendencias.md) se surgir).

## 5. Critérios de sucesso e DoD

### 5.1 Critérios de sucesso da sprint

- [ ] 3 enablers com critério de saída provado.
- [ ] 4 stories com DoD fechado (autenticação + isolamento em duas camadas testado).

### 5.2 Definition of Done (DoD)

**Referência:** DoD do projeto a definir em `docs/` — padrão mínimo: card com AC validados + evidência (PR/teste) + smoke test.

## 10. Decisões pendentes deste documento

1. `[ ]` Velocidade do time (primeira sprint — sem histórico) — calibrar na Retro.
