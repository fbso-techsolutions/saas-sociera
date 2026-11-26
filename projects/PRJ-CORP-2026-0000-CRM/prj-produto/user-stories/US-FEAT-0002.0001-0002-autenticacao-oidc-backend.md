# 💬 User Story: US-FEAT-0002.0001-0002 — Autenticar via OIDC no backend

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Mapeamento ágil** | [EPIC-0002](../epicos/EPIC-0002-identidade-multi-tenancy.md) ➔ [FEATURE-0002.0001](../features/FEATURE-0002.0001-autenticacao-oidc.md) ➔ `US-FEAT-0002.0001-0002` |
| **Prioridade** | Must |
| **Data-alvo** | Sprint 1 (07/12–18/12/2026) |
| **Estimativa** | 5 pontos |
| **Rastreio** | B-REQ-01 |
| **Versão** | 1.0 — layout INVEST/Gherkin |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Declaração da história

- **Como** usuário do CRM,
- **quero** autenticar via OIDC,
- **para** acessar as APIs protegidas com meu token.

## 2. Cenários comportamentais de aceite (Gherkin)

### Cenário 1: token válido
- **Dado que** tenho um token OIDC válido,
- **Quando** chamo uma rota protegida,
- **Então** a requisição é autenticada (200).

### Cenário 2: sem token
- **Dado que** não envio token,
- **Quando** chamo uma rota protegida,
- **Então** recebo 401.

### Cenário 3: token inválido
- **Dado que** envio um token inválido/expirado,
- **Quando** chamo uma rota protegida,
- **Então** recebo 401.

## 3. Regras de negócio relacionadas

- **`BR-0001`** — rota exige token, exceto healthcheck — *[FEATURE-0002.0001 §3](../features/FEATURE-0002.0001-autenticacao-oidc.md)*.

## 4. Não funcionais

- Validação de assinatura/expiração do JWT (sem chamada externa por request).

**Verificação INVEST** ([guia §1](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/agile/guia-invest-enablers-spike.md)): **I** ✅ · **N** ✅ · **V** ✅ · **E** ✅ · **S** ✅ · **T** ✅.
