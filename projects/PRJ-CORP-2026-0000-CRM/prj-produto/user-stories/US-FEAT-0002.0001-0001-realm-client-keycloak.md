# 💬 User Story: US-FEAT-0002.0001-0001 — Configurar realm e client Keycloak

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Mapeamento ágil** | [EPIC-0002](../epicos/EPIC-0002-identidade-multi-tenancy.md) ➔ [FEATURE-0002.0001](../features/FEATURE-0002.0001-autenticacao-oidc.md) ➔ `US-FEAT-0002.0001-0001` |
| **Prioridade** | Must |
| **Data-alvo** | Sprint 1 (07/12–18/12/2026) |
| **Estimativa** | 3 pontos |
| **Rastreio** | B-REQ-01 |
| **Versão** | 1.0 — layout INVEST/Gherkin |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Declaração da história

- **Como** Tech Lead,
- **quero** configurar o realm e o client do Keycloak (auto-hospedado) de forma versionada,
- **para** que o backend autentique usuários via OIDC.

## 2. Cenários comportamentais de aceite (Gherkin)

### Cenário 1: realm e client provisionados
- **Dado que** o Keycloak local está no ar,
- **Quando** aplico o realm/script de configuração,
- **Então** o realm e o client existem e o endpoint de issuer responde.

### Cenário 2: reprodutibilidade
- **Dado que** o ambiente foi destruído,
- **Quando** reaplico o script,
- **Então** o realm/client são recriados idênticos (config como código).

## 3. Regras de negócio relacionadas

- **`BR-0001`** — toda rota exige token — *definição na [FEATURE-0002.0001 §3](../features/FEATURE-0002.0001-autenticacao-oidc.md)*.

## 4. Não funcionais

- Config versionada (sem ajuste manual na UI).

**Verificação INVEST** ([guia §1](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/agile/guia-invest-enablers-spike.md)): **I** ✅ · **N** ✅ · **V** ✅ · **E** ✅ · **S** ✅ · **T** ✅.
