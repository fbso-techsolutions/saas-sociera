# 🎯 INTENT — FBSO CRM

> **O que este repositório é, por que existe e para onde vai.** Leitura obrigatória para qualquer
> agente (IA ou humano) antes de tocar em qualquer arquivo. Processo vive em [AGENTS.md](AGENTS.md)
> e na [platform-standards](https://github.com/fbso-techsolutions/platform-standards).

## 1. O que é

CRM próprio (simples) da **FBSO Technology Solutions** — produto SaaS multi-tenant. Núcleo de
relacionamento (pessoas, organizações e papéis), funil comercial e, em evolução, atendimento
(tickets/SLA). Primeira validação: operação comercial da **FBSO Tech Services** (dogfooding);
depois, hub de relacionamento e integração dos SaaS **Educatio**, **Fiscalia**, **Mercator** e
**Materiae**.

> Decisão de origem: [PENDENCY-0018](https://github.com/fbso-techsolutions/portal-fbso) — "CRM
> próprio (simples), novo produto da empresa". Gatilho imediato: `portal-fbso` FEATURE-0006.0003.

## 2. Objetivo do MVP (Trilha A — simples)

1. Isolamento por tenant + identidade (Keycloak auto-hospedado).
2. Cadastro de pessoas e organizações (Party + PartyRole).
3. Pipeline comercial e oportunidades (Deal) em Kanban.
4. Tarefas e registro de interações.
5. Auditoria das operações relevantes.
6. **Ingestão de leads do portal** — contrato de solução (OpenAPI + SDK + webhook), desbloqueando
   a Release 2 do `portal-fbso` (FEATURE-0006.0003).

> **Fora do MVP** (evolução): Kestra, mensageria dedicada, mobile, IA, templates de indústria,
> marketplace de processos.

## 3. Roadmap

Fase 0 (preparação) → Fase 1 (core + FBSO Tech Services) → Fase 2 (atendimento/SLA + eventos) →
Fase 3 (1ª integração vertical) → Fase 4 (comercialização SaaS). Detalhe e cortes:
[`docs/`](docs/README.md) e [PRD](../projects/PRJ-CORP-2026-0000-CRM/PRD.md).

## 4. Stack

Fonte única: [AGENTS.md §5](AGENTS.md) — Java 25 + Quarkus · PostgreSQL 17 (RLS) · Flyway ·
React + TS (web) · Keycloak auto-hospedado.

## 5. Decisões ainda abertas

1. **Nome de marca** do CRM (hoje "FBSO CRM"; a família usa marcas — Educatio, Mercator…).
2. **Domínio próprio** (ADR-002 de domínios não cobre o CRM ainda).
3. **Kestra** — componente novo de plataforma; exige ADR antes de entrar no MVP.
4. **Mensageria dedicada** (Kafka/RabbitMQ/Redis) — adiada; guardrail manda Outbox no monólito.
5. **Frontend mobile** — React Native (evolução); pasta reservada em `frontend/mobile/`.
