# ⚙️ TASK-0001 — Estrutura do monorepo (bases Quarkus + React)

| Campo | Valor |
|---|---|
| **Origem** | [ENABLER-0001 — Repositório e estrutura](../enablers/ENABLER-0001-repositorio-estrutura.md) |
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Sprint** | [Sprint 1 — Fundação e Multi-tenancy](../../prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) |
| **Dono** | Romeu Augusto |
| **Esforço** | 4h |
| **Depende de** | — |

## 1. Objetivo

Criar a estrutura do monorepo e as bases compiláveis de backend (Quarkus) e frontend (React+Vite).

## 2. O que implementar/entregar

- Criar `backend/` (Quarkus + pom, módulos) e `frontend/web/` (Vite + React + TS).
- Adicionar `.gitignore`, READMEs de pasta e convenções referenciando a platform-standards.

## 3. Critério de saída

- [ ] `mvn -q compile` (backend) e `npm install && npm run typecheck` (frontend) passam do zero.
