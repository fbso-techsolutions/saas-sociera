# 🧭 EPIC-0004 — Papéis e Relacionamentos

| Campo | Valor |
|---|---|
| Projeto | FBSO CRM · PRJ-CORP-2026-0000-CRM |
| Épico | `EPIC-0004` — Papéis e Relacionamentos |
| B-REQs atendidas | B-REQ-03 |
| Features | 2 — `FEATURE-0004.0001` · `FEATURE-0004.0002` |
| Prioridade | Onda 2-Should (Fase 1) |
| Status | 📝 Rascunho (2026-11-26) |

## 1. Objetivo

- **Problema:** um participante pode ser lead, cliente e parceiro ao mesmo tempo; sem papéis e
  relacionamentos, essa flexibilidade se perde.
- **Solução:** `PartyRole` (papéis com validade) e `Relationship` (vínculos entre parties).
- **Impacto:** representação fiel do relacionamento comercial, sem duplicar cadastro.

## 2. Fora do escopo

- Papéis setoriais específicos (Aluno/Contador/Reciclador) — EPIC-0015 (templates).
- Validação de hierarquias complexas de relacionamento (evolução).

## 3. Features derivadas

| Feature | Título | Stories |
|---|---|---|
| `FEATURE-0004.0001` | Papéis de Party (PartyRole) | — (sem card) |
| `FEATURE-0004.0002` | Relacionamentos entre Parties | — (sem card) |

## 4. Decisões pendentes

1. `[ ]` Regras de validade/encerramento de papéis (sem apagar histórico).
