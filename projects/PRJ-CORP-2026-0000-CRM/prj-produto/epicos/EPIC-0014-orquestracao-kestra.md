# 🧭 EPIC-0014 — Orquestração Kestra

| Campo | Valor |
|---|---|
| Projeto | FBSO CRM · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0014` — Orquestração Kestra |
| B-REQs atendidas | B-REQ-10 |
| Features | 3 — `FEATURE-0014.0001` … `FEATURE-0014.0003` |
| Prioridade | Onda 3-Could (Fase 3) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** processos cross-system (onboarding, aprovações, integrações) não devem ser
  codificados no domínio transacional.
- **Solução:** Kestra como camada de orquestração (fluxos YAML versionados), desacoplada do CRUD.
- **Impacto:** processos auditáveis e customizáveis sem redeploy do backend.

## 2. Fora do escopo

- ⚠️ **MVP** — Kestra é componente novo de plataforma; **bloqueado** até ADR (PENDENCY-0003).
- Substituir o domínio transacional (Kestra orquestra, não implementa regras).

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0014.0001` | Fluxos de onboarding | — (sem card) |
| `FEATURE-0014.0002` | Fluxos de SLA/escalonamento | — (sem card) |
| `FEATURE-0014.0003` | Fluxos cross-SaaS | — (sem card) |

## 4. Decisões pendentes

1. `[ ]` **ADR de plataforma** para Kestra (blueprint + operação) — [PENDENCY-0003](../../../pendencias.md).
