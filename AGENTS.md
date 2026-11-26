# 🤖 AGENTS — Regras de operação (FBSO CRM)

> Regras de trabalho **neste repositório**. A constituição da org vive na
> [`platform-standards`](https://github.com/fbso-techsolutions/platform-standards) — **linke, não
> copie**. Leia o [INTENT.md](INTENT.md) antes de qualquer coisa.

## 1. Convenções da org (obrigatórias)

- **"Promover o genérico, manter o específico."** O que é transversal sobe para `platform-standards`.
- **"Aponta, não copia."** Um documento vive em um só lugar.
- **IDs de entidades** seguem `{ENTIDADE}-{NNNN}`: [padrão](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/agile/padrao-identificacao-entidades.md).

## 2. Status e estrutura

🚧 **Em planejamento** — repositório esqueleto. Estrutura segue o padrão do `saas-materiae`
(ex-`saas-rmr`), consumindo a `platform-standards`. Frontend dividido em `frontend/web/` +
`frontend/mobile/` (mobile = evolução). `workflows/kestra/` reservado (evolução).

## 3. Onde cada coisa vive — leia conforme a tarefa

| Quando a tarefa é… | Leia | O que responde |
|---|---|---|
| Iniciar a sessão | [INTENT.md](INTENT.md) | O que é o CRM, para onde vai |
| Visão / escopo / domínio | [docs/](docs/README.md) | Por quê, entidades, capacidades (a conformar) |
| Entregas (PRD, backlog, sprints) | [projects/](projects) | O que será entregue (a criar) |
| Escrever / alterar código | [platform-standards/standards/engineering/](https://github.com/fbso-techsolutions/platform-standards/tree/main/standards/engineering) · [agile/](https://github.com/fbso-techsolutions/platform-standards/tree/main/standards/agile) | Padrões de código, commits, IDs |
| Arquitetura / eventos / integrações | [platform-standards/standards/architecture/](https://github.com/fbso-techsolutions/platform-standards/tree/main/standards/architecture) | Monólito modular, Outbox/ACL, API-First |
| Auth / dados sensíveis | [platform-standards/standards/security/SECURITY.md](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/security/SECURITY.md) | Baseline de segurança (fonte única) |

## 4. Limites

- **Não** inventar IDs, donos, datas ou escopo — usar `— (a preencher)`.
- **Não** alterar `platform-standards/` sem decisão explícita (registrar ADR/pendência).
- **Não** importar o plano de `.temporaria/ideias/crm/` para `docs/` sem conformar: IDs
  `EP-01…` → `EPIC-{NNNN}` (cadeia `B-REQ → épico → feature → story`), stack (Java 25 ·
  PostgreSQL 17+ · Flyway · Keycloak) e referências a `platform-standards` (Outbox, monólito
  modular, integrações ADR-001/ADR-002, multi-tenancy/RLS/RBAC/auditoria).

## 5. Stack do código (ao implementar)

Java 25 + Quarkus (Mandrel) · PostgreSQL 17+ (RLS) · Flyway · React + TypeScript (web) ·
Keycloak auto-hospedado. MVP em Docker Compose; K8s + ArgoCD + Helm = alvo SaaS.
