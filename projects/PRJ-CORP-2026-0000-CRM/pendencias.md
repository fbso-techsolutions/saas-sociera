# 🎯 Hub de Pendências — Sociera

> Questões que exigem **resposta/decisão** (dono + prazo) antes de avançar. Fonte única — itens de
> trabalho ficam no projeto ([PRD.md](PRD.md) · [rastreabilidade](prj-produto/rastreabilidade.md));
> decisão pendente fica aqui. Donos existem como papel no [equipe.md](equipe.md).

## Abertas

| ID | Pendência | Dono | Prazo | Status |
|---|---|---|---|---|
| PENDENCY-0003 | Kestra como componente de plataforma — exige ADR + blueprint na `platform-standards` antes de entrar no MVP | Arquiteto + Tech lead | — | ⬜ aberta |
| PENDENCY-0005 | Frontend mobile (React Native) — evolução; estrutura reservada em `frontend/mobile/` | PM/PO + Engenharia | — | ⬜ aberta |
| PENDENCY-0008 | Aplicar os 3 rulesets org-level na `fbso-techsolutions` (`develop` · `release/*` · `main`). **Ordem:** (1) criar times `sociera`+`devops` → (2) rulesets `release/*` e `main` → (3) ruleset `develop` só após o CI (ENABLER-0003) com check `lint → typecheck → test`. **Dependências:** time `sociera` no CODEOWNERS (review de code owner) · `bypass_actors` do back-merge | Arquiteto + Tech lead + Infra | — | ⬜ aberta |

## Respondidas

| ID | Pendência | Decisão | Data |
|---|---|---|---|
| — | CRM alvo | ✅ **Sociera** — CRM próprio (simples), novo produto (origem: PENDENCY-0018 do portal-fbso) | 2026-11-23 |
| — | ID do projeto | ✅ `PRJ-CORP-2026-0000-CRM` (área `CORP`) | 2026-11-26 |
| PENDENCY-0001 | Nome de marca | ✅ **Sociera** | 2026-11-26 |
| PENDENCY-0002 | Domínio próprio | ✅ **fbsosociera.com.br** | 2026-11-26 |
| PENDENCY-0004 | Mensageria dedicada | ✅ **Outbox + scheduler Quarkus + webhook HTTP** (sem broker no MVP); Kafka/RabbitMQ só se volume exigir — [ADR-004](../../docs/tecnico/arquitetura/adrs/adr-004-mensageria-outbox-scheduler.md) | 2026-11-26 |
| PENDENCY-0006 | Time/squad do CRM | ✅ **definido e alocado** — nomes + % em [equipe.md](equipe.md) | 2026-11-26 |
| PENDENCY-0007 | URL base + escopos do contrato de leads | ✅ **PRD/HML/DEV** (`api.{,hml.,dev.}fbsosociera.com.br`) + escopos `leads:read`/`leads:write` — [contrato](../../docs/tecnico/arquitetura/integracoes/contratos/openapi-ingestao-leads.yaml) | 2026-11-26 |

> **Ritual:** atualizar a cada decisão; dono deve existir no [equipe.md](equipe.md).
