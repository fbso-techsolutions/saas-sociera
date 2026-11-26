# ✨ FEATURE-0002.0003 — RBAC (papéis e permissões)

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Épico** | [EPIC-0002 — Identidade e Multi-tenancy](../epicos/EPIC-0002-identidade-multi-tenancy.md) |
| **B-REQ dona** | B-REQ-01 |
| **Prioridade** | Onda 2-Should (MVP completo) |
| **Requisitos** | B-REQ-01 |
| **Depende de** | FEATURE-0002.0001 (auth OIDC) |
| **Entra depois** | — |
| **User stories** | — (a criar) |
| **🔒 Travada por** | — (livre) |
| **Status** | 📝 Rascunho (2026-11-26) |

## 1. Objetivo de negócio

Controlar o que cada usuário pode ver/fazer dentro do tenant (papéis e permissões), sem expor
dados de outros contextos.

## 2. Escopo

### Entra
- Papéis e permissões (RBAC) mapeados ao Keycloak.
- Autorização por recurso/ação.

### Fora (nesta feature)
- Administração self-service de tenant → Fase 4.

## 7. Critérios de aceite da feature (DoD)

- [ ] Usuário sem permissão é bloqueado (403) na ação protegida.

## 8. Decisões pendentes deste documento

1. `[ ]` Matriz de papéis × recursos — refinamento da Sprint 2 (dono: PM/PO + Tech Lead).
