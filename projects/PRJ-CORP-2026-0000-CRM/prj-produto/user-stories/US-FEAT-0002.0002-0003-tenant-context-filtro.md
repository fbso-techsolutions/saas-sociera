# 💬 User Story: US-FEAT-0002.0002-0003 — Derivar tenant_id do token e filtrar queries

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Mapeamento ágil** | [EPIC-0002](../epicos/EPIC-0002-identidade-multi-tenancy.md) ➔ [FEATURE-0002.0002](../features/FEATURE-0002.0002-contexto-tenant.md) ➔ `US-FEAT-0002.0002-0003` |
| **Prioridade** | Must |
| **Data-alvo** | Sprint 1 (07/12–18/12/2026) |
| **Estimativa** | 5 pontos |
| **Rastreio** | B-REQ-01 |
| **Versão** | 1.0 — layout INVEST/Gherkin |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Declaração da história

- **Como** sistema,
- **quero** derivar o `tenant_id` do token autenticado e filtrar toda query por ele,
- **para** isolar os dados de cada organização.

## 2. Cenários comportamentais de aceite (Gherkin)

### Cenário 1: usuário vê só o próprio tenant
- **Dado que** sou usuário do tenant A,
- **Quando** consulto parties/deals,
- **Então** só recebo dados do tenant A.

### Cenário 2: tenant forjado no payload é negado
- **Dado que** envio um `tenant_id` de outro tenant no body,
- **Quando** a operação é processada,
- **Então** o tenant usado é o do token (o forjado é ignorado).

### Cenário 3: sem tenant no token
- **Dado que** o token não carrega tenant,
- **Quando** tento acessar dados,
- **Então** recebo erro de autorização.

## 3. Regras de negócio relacionadas

- **`BR-0003`** · **`BR-0004`** — filtro obrigatório e tenant do contexto — *[FEATURE-0002.0002 §3](../features/FEATURE-0002.0002-contexto-tenant.md)*.

## 4. Não funcionais

- Filtro via Hibernate `@FilterDef`/`@Filter` (Panache), aplicado também a query nativa.

**Verificação INVEST** ([guia §1](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/agile/guia-invest-enablers-spike.md)): **I** ✅ · **N** ✅ · **V** ✅ · **E** ✅ · **S** ✅ · **T** ✅.
