# 🔧 ENABLER-0001 — Repositório e estrutura monorepo

| Campo | Valor |
|---|---|
| **Categoria** | Infraestrutura |
| **Origem** | EPIC-0001 — Fundação e Engenharia (Fase 0) |
| **Habilita** | todas as features (base de qualquer entrega) |
| **Depende de** | — |
| **Dono sugerido** | Romeu Augusto (Tech Lead) |
| **Estimativa (Job Size)** | 3 |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Visão Geral e Contexto

- **Categoria:** Infraestrutura.
- **Origem:** EPIC-0001 (fundação de engenharia).
- **Status de Bloqueio:** Bloqueador crítico — sem repositório/estrutura, nenhuma feature pode
  começar.

## 2. Análise de Priorização (WSJF)

- **Valor de Negócio:** habilita toda a entrega subsequente.
- **Habilitação de Oportunidade:** destrava o monorepo Quarkus + React + Kestra (reservado).

## 3. Escopo Técnico Detalhado

1. Estruturar o monorepo (`backend/`, `frontend/web/`, `infra/`, `docs/`, `projects/`).
2. Criar base Quarkus (pom + módulos) e base React (Vite + TS).
3. Adicionar `.gitignore`, READMEs de pasta e convenções (commit/branch) referenciando a platform-standards.

> **Não** inclui: docker-compose (ENABLER-0002) nem CI (ENABLER-0003).

## 4. Critérios de Saída (DoD)

- [ ] `mvn -q compile` (backend) e `npm install && npm run typecheck` (frontend) passam do zero.
- [ ] Estrutura de pastas segue o padrão do `saas-materiae`.
