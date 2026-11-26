# 🏗️ Arquitetura — FBSO CRM

> Viabilidade técnica persistente. Fonte: `.temporaria/ideias/crm/`, conformada à `platform-standards`.

## 1. Visão lógica

```text
                Usuários
                   |
         React + TypeScript (web)
                   |
             API REST / HTTPS
                   |
         Java 25 + Quarkus (monólito modular)
                   |
      +------------+------------+
      |            |            |
  Domínio CRM   Segurança     Auditoria
  Parties/Roles  OAuth2/OIDC  Audit Logs
  Deals/Pipelines RBAC
                   |
             PostgreSQL 17+ (RLS)
                   |
           Outbox de Eventos
                   |
      Webhooks / Mensageria (evolução)
                   |
        Kestra (evolução — fora do MVP)
```

> Implantação incremental; nem todos os componentes ativos no primeiro incremento.

## 2. Stack (conformada)

| Camada | Tecnologia | Diretriz |
|---|---|---|
| Backend | Java **25** + Quarkus (Mandrel) | Padrão da org (`saas-materiae`) |
| Persistência | PostgreSQL **17+** (RLS) | UUID e JSONB onde fizer sentido |
| Migrações | **Flyway** | Padrão da org |
| Frontend web | React + TypeScript + Vite | `coding-standards-react.md` |
| Frontend mobile | React Native + Expo | Evolução (reservado) |
| Identidade | **Keycloak auto-hospedado** | Padrão da org (não Auth0) |
| Orquestração | Kestra | Evolução — exige ADR de plataforma |
| Mensageria | Outbox no monólito; broker só se justificar | Guardrail de eventos |
| CI/CD | GitHub Actions · Docker Compose (MVP) · K8s + ArgoCD + Helm (alvo SaaS) | Padrão da org |

## 3. Responsabilidades por componente

- **Quarkus:** regras transacionais, APIs REST, validação/autorização, persistência, auditoria,
  geração de eventos na Outbox.
- **PostgreSQL:** dados transacionais, segregação por tenant (RLS), JSONB, Outbox.
- **Frontend:** operação comercial/atendimento; consome **exclusivamente** os contratos de API.
- **Kestra (evolução):** orquestração de processos e integrações desacopladas do domínio.

## 4. Multi-tenancy, segurança e governança

Isolamento em **duas camadas** (meta: incidente zero — [ADR-002](adrs/adr-002-multi-tenant-duas-camadas.md)):

1. **Aplicação (Quarkus):** filtro automático do Hibernate (`@FilterDef`/`@Filter` no Panache)
   injetando o `tenant_id` extraído do token JWT em toda query.
2. **Banco (PostgreSQL):** Row-Level Security via `SET LOCAL app.current_tenant = '<uuid>'` na
   conexão transacional — se uma query nativa esquecer o filtro, o banco bloqueia.

Acima disso: OAuth 2.0/OIDC, RBAC, verificação de tenant em toda operação, auditoria imutável,
segredos seguros, criptografia em trânsito/repouso, logs sem exposição de dados pessoais, testes
de tentativa de acesso entre tenants, backup/recuperação.

> **Critério de bloqueio:** nenhuma entrega que manipule dados de negócio está pronta sem testes
> provando que um tenant não acessa dados de outro.
> Baseline: [platform-standards/security/SECURITY.md](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/security/SECURITY.md).

## 5. APIs, eventos e integrações

- **API-first:** OpenAPI/Swagger, contratos versionados, paginação/filtros/erros consistentes.
- **Eventos:** nomes semânticos versionados (ex.: `lead.created`, `deal.stage_changed`), JSON
  tipado — padrão final consolidado antes da 1ª integração externa.
- **Outbox (relay):** operação + evento na mesma transação; um **scheduler no Quarkus** relê a
  `outbox_events` e dispara **webhooks HTTP** — **sem broker no MVP** ([ADR-004](adrs/adr-004-mensageria-outbox-scheduler.md));
  Kafka/RabbitMQ só se o volume exigir. Consumidores idempotentes. Guardrail:
  [guardrail-eventos-outbox.md](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/architecture/guardrail-eventos-outbox.md).
- **Integrações:** padrão Port → Adapter (ACL); contrato de solução (OpenAPI + SDK + eventos).
  [ADR-001](https://github.com/fbso-techsolutions/platform-standards/blob/main/governance/adrs/adr-001-estrategia-integracoes.md).
