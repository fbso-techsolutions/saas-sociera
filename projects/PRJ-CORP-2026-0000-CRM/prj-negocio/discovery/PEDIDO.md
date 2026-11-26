# 📄 PEDIDO — Demanda de origem

| Campo | Valor |
|---|---|
| Projeto | Sociera · PRJ-CORP-2026-0000-CRM |
| Solicitante | FBSO Technology Solutions |
| Origem | [PENDENCY-0018 do portal-fbso](https://github.com/fbso-techsolutions/portal-fbso) — "CRM próprio (simples), novo produto" |
| Status | ✅ Registrada (2026-11-26) |

## 1. O que se pede

Criar a **Sociera** — CRM próprio (simples) da FBSO Technology Solutions — SaaS multi-tenant. Núcleo de
relacionamento (pessoas, organizações, papéis), funil comercial (pipeline + oportunidades) e, em
evolução, atendimento (tickets/SLA). Primeiro cliente: a própria **FBSO Tech Services**.

## 2. Evolução esperada

1. **Fase 0** — preparação e decisões técnicas (repo, ambientes, padrões, ADRs).
2. **Fase 1** — core CRM + operação FBSO Tech Services (multi-tenancy, Parties, Pipeline, Deals,
   tarefas, auditoria, **ingestão de leads do portal**).
3. **Fase 2** — atendimento/SLA + eventos (Outbox, webhooks).
4. **Fase 3** — primeira integração vertical (SaaS) + orquestração Kestra.
5. **Fase 4** — comercialização SaaS (templates de indústria, IA).

## 3. Preferências técnicas

- **Stack (conformada à org):** Java 25 + Quarkus (Mandrel) · PostgreSQL 17+ (RLS) · Flyway ·
  React + TypeScript (web) · Keycloak auto-hospedado.
- **Hospedagem:** Docker Compose no MVP; K8s + ArgoCD + Helm como alvo SaaS.
- **Fora do MVP:** Kestra, mensageria dedicada, mobile (React Native), IA.

## 4. Contexto e referências

- Gatilho imediato: `portal-fbso` [FEATURE-0006.0003 — Integração CRM](https://github.com/fbso-techsolutions/portal-fbso) (leads do portal → CRM).
- Levantamento: `.temporaria/ideias/crm/` (`FBSO CRM - IDEIAS - 0001.md` · `PLANO-IMPLEMENTACAO-FBSO-CRM.md`).

> Detalhes completos no [INTENT.md](../../../INTENT.md) e na [visão](../../../docs/negocio/visao.md).
