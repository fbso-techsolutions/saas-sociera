# 🎯 Hub de Pendências — FBSO CRM

> Questões que exigem **resposta/decisão** (dono + prazo) antes de avançar. Fonte única — itens de
> trabalho ficam no projeto ([PRD.md](PRD.md) · [rastreabilidade](prj-produto/rastreabilidade.md));
> decisão pendente fica aqui. Donos existem como papel no [equipe.md](equipe.md).

## Abertas

| ID | Pendência | Dono | Prazo | Status |
|---|---|---|---|---|
| PENDENCY-0001 | Nome de marca do CRM (hoje "FBSO CRM"; a família usa marcas — Educatio, Mercator…) | PM/PO + Brand/Design | — | ⬜ aberta |
| PENDENCY-0002 | Domínio próprio do CRM (ADR-002 de domínios não cobre o CRM ainda) | PM/PO + Tech lead | — | ⬜ aberta |
| PENDENCY-0003 | Kestra como componente de plataforma — exige ADR + blueprint na `platform-standards` antes de entrar no MVP | Arquiteto + Tech lead | — | ⬜ aberta |
| PENDENCY-0005 | Frontend mobile (React Native) — evolução; estrutura reservada em `frontend/mobile/` | PM/PO + Engenharia | — | ⬜ aberta |
| PENDENCY-0006 | Time/squad do CRM (papéis e alocação) | PM/PO | — | ⬜ aberta |

## Respondidas

| ID | Pendência | Decisão | Data |
|---|---|---|---|
| — | CRM alvo | ✅ **CRM próprio (simples)** — novo produto (origem: PENDENCY-0018 do portal-fbso) | 2026-11-23 |
| — | ID do projeto | ✅ `PRJ-CORP-2026-0000-CRM` (área `CORP`) | 2026-11-26 |
| PENDENCY-0004 | Mensageria dedicada | ✅ **Outbox + scheduler Quarkus + webhook HTTP** (sem broker no MVP); Kafka/RabbitMQ só se volume exigir — [ADR-004](../../docs/tecnico/arquitetura/adrs/adr-004-mensageria-outbox-scheduler.md) | 2026-11-26 |

> **Ritual:** atualizar a cada decisão; dono deve existir no [equipe.md](equipe.md).
