# ✨ FEATURE-0002.0002 — Contexto de Tenant

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Épico** | [EPIC-0002 — Identidade e Multi-tenancy](../epicos/EPIC-0002-identidade-multi-tenancy.md) |
| **B-REQ dona** | B-REQ-01 |
| **Prioridade** | Onda 1-Must (MVP) |
| **Requisitos** | B-REQ-01 |
| **Depende de** | FEATURE-0002.0001 (auth OIDC) |
| **Entra depois** | FEATURE-0002.0004 (segregação/RLS) |
| **User stories** | [US-0003](...) |
| **🔒 Travada por** | — (livre) |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Objetivo de negócio

Garantir que toda operação de leitura/escrita seja automaticamente escopada ao tenant do usuário
autenticado — a base do isolamento multi-tenant (meta: incidente zero).

## 2. Escopo

### Entra
- Resolução do `tenant_id` a partir do token JWT autenticado.
- Filtro automático do Hibernate (`@FilterDef`/`@Filter` no Panache) em toda query.

### Fora (nesta feature)
- Row-Level Security no banco → FEATURE-0002.0004.
- Atributos customizados por tenant → FEATURE-0003.0003.

## 3. Regras de negócio

| ID | Regra |
|---|---|
| BR-0003 | Nenhuma query pode escapar do filtro de tenant; query nativa também passa pelo filtro. |
| BR-0004 | `tenant_id` nunca vem de parâmetro do cliente — sempre do contexto autenticado. |

## 5. User stories desta feature

| ID | História | Critérios |
|---|---|---|
| `US-FEAT-0002.0002-0003` | Derivar tenant_id do token e filtrar queries | 3 AC |

## 7. Critérios de aceite da feature (DoD)

- [ ] Toda query de entidade multitenant filtra por `tenant_id` automaticamente.
- [ ] Tentativa de acesso com tenant forjado no payload é negada.

## 8. Decisões pendentes deste documento

1. `[ ]` Confirmar a estratégia `@Filter` vs `@FilterDef` por entity — no refinamento técnico.
