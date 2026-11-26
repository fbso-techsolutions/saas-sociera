# 🧭 EPIC-0001 — Fundação e Engenharia

| Campo | Valor |
|---|---|
| Projeto | Sociera · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0001` — Fundação e Engenharia |
| B-REQs atendidas | — (enabler de habilitação) |
| Features | 4 — `FEATURE-0001.0001` … `FEATURE-0001.0004` |
| Prioridade | Onda 1-Must (Fase 0) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** sem repositório, ambientes e padrões, não há base para evoluir o produto com
  qualidade e multi-tenancy desde a primeira linha.
- **Solução:** subir o monorepo (Quarkus + React web), ambiente local (Docker Compose), CI e ADRs.
- **Impacto:** fundação de engenharia que destrava os demais épicos.

## 2. Fora do escopo

- Kestra, mensageria dedicada e mobile (evolução — fora do MVP).
- Templates de indústria e IA.

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0001.0001` | Repositório e estrutura monorepo | — (sem card) |
| `FEATURE-0001.0002` | Ambientes locais (Docker Compose) | — (sem card) |
| `FEATURE-0001.0003` | Padrões de código e CI | — (sem card) |
| `FEATURE-0001.0004` | ADRs de decisões arquiteturais | — (sem card) |

## 4. Decisões pendentes

1. `[ ]` Versão Java (org já usa **25** — confirmar sem reabrir) e estratégia de hospedagem.
2. `[ ]` Escopo exato do CI (Quarkus + React) — no refinamento.
