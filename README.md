# FBSO CRM

> **CRM próprio da FBSO — relacionamento, vendas e atendimento do ecossistema.**

SaaS CRM multi-tenant. Núcleo de relacionamento (pessoas, organizações, papéis), funil
comercial e, em evolução, atendimento (tickets/SLA). Primeira validação: operação comercial da
**FBSO Tech Services**; em seguida, hub de relacionamento e integração dos SaaS (**Educatio**,
**Fiscalia**, **Mercator**, **Materiae**).

## Status

🚧 **Em planejamento** — repositório esqueleto. Estrutura criada; desenvolvimento ainda não
iniciado. Fonte de produto: plano em `.temporaria/ideias/crm/` (a conformar e promover para
[`docs/`](docs/README.md)).

## Onde está o quê

| Caminho | Conteúdo |
|---|---|
| [docs/](docs) | **Produto** — visão, negócio, domínio, arquitetura, segurança (persistente) |
| [projects/](projects) | **Projetos** — um folder por entrega (PRD → negócio → produto → técnico) |
| [backend/](backend) | Backend Quarkus (monólito modular) |
| [frontend/web/](frontend/web) | Frontend web React SPA |
| [frontend/mobile/](frontend/mobile) | Frontend mobile React Native (evolução — reservado) |
| [workflows/kestra/](workflows/kestra) | Fluxos de orquestração Kestra (evolução — reservado) |
| [infra/](infra) | docker-compose (MVP) + helm + keycloak |

## Stack (MVP)

Java 25 + Quarkus (Mandrel) · PostgreSQL 17+ (RLS) · Flyway · React + TypeScript (web) ·
Keycloak auto-hospedado — MVP em Docker Compose. K8s + ArgoCD + Helm = alvo SaaS.
**Fora do MVP** (evolução): Kestra, mensageria dedicada, mobile, IA.

## Regras

- "Promover o genérico, manter o específico" — ver [platform-standards/standards/](https://github.com/fbso-techsolutions/platform-standards).
- Visão e escopo: [docs/README.md](docs/README.md) (a conformar a partir do plano).
