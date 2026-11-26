# 🧭 EPIC-0003 — Cadastro de Parties

| Campo | Valor |
|---|---|
| Projeto | Sociera · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0003` — Cadastro de Parties |
| B-REQs atendidas | B-REQ-02 |
| Features | 3 — `FEATURE-0003.0001` … `FEATURE-0003.0003` |
| Prioridade | Onda 1-Must (Fase 1) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** cadastros isolados e rígidos por tipo (cliente/lead/fornecedor) impedem representar
  o mesmo participante em vários contextos e geram duplicação.
- **Solução:** entidade única `Party` (PF/PJ) com atributos customizados (JSONB) e busca/filtros.
- **Impacto:** cadastro consistente e reutilizável em todo o relacionamento.

## 2. Fora do escopo

- Papéis e relacionamentos (EPIC-0004).
- Campos customizados como substituto do modelo relacional (só extensibilidade).

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0003.0001` | Cadastro de PF/PJ (Party) | — (sem card) |
| `FEATURE-0003.0002` | Busca e filtros de Parties | — (sem card) |
| `FEATURE-0003.0003` | Atributos customizados (JSONB) | — (sem card) |

## 4. Decisões pendentes

1. `[ ]` Unicidade de identificadores fiscais por tenant (política).
