# 🔧 ENABLER-0003 — CI (GitHub Actions)

| Campo | Valor |
|---|---|
| **Categoria** | Infraestrutura |
| **Origem** | EPIC-0001 — Fundação e Engenharia (Fase 0) |
| **Habilita** | todas as features (gate de qualidade antes do merge) |
| **Depende de** | ENABLER-0001 (estrutura) |
| **Dono sugerido** | Romeu Augusto (Tech Lead) |
| **Estimativa (Job Size)** | 2 |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Visão Geral e Contexto

- **Categoria:** Infraestrutura (DevOps).
- **Origem:** EPIC-0001.
- **Status de Bloqueio:** Habilitador de cadência — sem CI, não há gate de qualidade no PR.

## 2. Análise de Priorização (WSJF)

- **Valor de Negócio:** protege a branch principal.
- **Habilitação de Oportunidade:** base para deploy contínuo (alvo SaaS).

## 3. Escopo Técnico Detalhado

1. Workflow CI no PR: build + testes (Quarkus) e lint/typecheck/test (React).
2. Reusar os workflows da `platform-standards/.github/workflows/` (via `uses:`).

> **Não** inclui: deploy (evolução) nem branch protection (config GitHub à parte).

## 4. Critérios de Saída (DoD)

- [ ] PR aberto dispara CI e falha com código quebrado.
- [ ] Check verde bloqueia merge (status check configurado).
