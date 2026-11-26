# 💬 User Story: US-FEAT-0002.0004-0004 — Aplicar RLS e testar isolamento entre tenants

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Mapeamento ágil** | [EPIC-0002](../epicos/EPIC-0002-identidade-multi-tenancy.md) ➔ [FEATURE-0002.0004](../features/FEATURE-0002.0004-segregacao-multi-tenant.md) ➔ `US-FEAT-0002.0004-0004` |
| **Prioridade** | Must |
| **Data-alvo** | Sprint 1 (07/12–18/12/2026) |
| **Estimativa** | 5 pontos |
| **Rastreio** | B-REQ-01 |
| **Versão** | 1.0 — layout INVEST/Gherkin |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Declaração da história

- **Como** responsável pela plataforma,
- **quero** aplicar Row-Level Security no PostgreSQL e um teste de isolamento,
- **para** provar que um tenant não acessa dados de outro (meta: incidente zero).

## 2. Cenários comportamentais de aceite (Gherkin)

### Cenário 1: tenant A não lê tenant B
- **Dado que** existem dados dos tenants A e B,
- **Quando** a conexão do tenant A consulta,
- **Então** só os dados de A retornam (RLS bloqueia B).

### Cenário 2: sem contexto de tenant, acesso negado
- **Dado que** `app.current_tenant` não foi definido,
- **Quando** uma query é executada,
- **Então** o banco nega acesso (fail-closed).

### Cenário 3: teste automatizado
- **Dado que** o teste de isolamento existe,
- **Quando** a suíte roda,
- **Então** o cenário de cross-tenant é verificado automaticamente.

## 3. Regras de negócio relacionadas

- **`BR-0005`** — sem `app.current_tenant`, nega — *[FEATURE-0002.0004 §3](../features/FEATURE-0002.0004-segregacao-multi-tenant.md)*.

## 4. Não funcionais

- RLS via `SET LOCAL app.current_tenant = '<uuid>'` na conexão transacional.

**Verificação INVEST** ([guia §1](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/agile/guia-invest-enablers-spike.md)): **I** ✅ · **N** ✅ · **V** ✅ · **E** ✅ · **S** ✅ · **T** ✅.
