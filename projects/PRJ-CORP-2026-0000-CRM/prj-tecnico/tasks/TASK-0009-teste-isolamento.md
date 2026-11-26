# ⚙️ TASK-0009 — Teste de isolamento entre tenants

| Campo | Valor |
|---|---|
| **Origem** | [US-FEAT-0002.0004-0004 — RLS + isolamento](../../prj-produto/user-stories/US-FEAT-0002.0004-0004-rls-isolamento.md) |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | [Sprint 1](../../prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) |
| **Dono** | Patricia Varra |
| **Esforço** | 4h |
| **Depende de** | [TASK-0008](TASK-0008-rls.md) |

## 1. Objetivo

Provar, por teste automatizado, que um tenant não acessa dados de outro.

## 2. O que implementar/entregar

- Teste de integração cross-tenant (tenant A tenta ler/escrever B).

## 3. Critério de saída

- [ ] Teste falha o acesso cruzado e a suíte roda verde no CI.
