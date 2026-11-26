# ✨ FEATURE-0002.0001 — Autenticação OIDC (Keycloak)

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Épico** | [EPIC-0002 — Identidade e Multi-tenancy](../epicos/EPIC-0002-identidade-multi-tenancy.md) |
| **B-REQ dona** | B-REQ-01 |
| **Prioridade** | Onda 1-Must (MVP) |
| **Requisitos** | B-REQ-01 |
| **Depende de** | ENABLER-0002 (ambientes) |
| **Entra depois** | FEATURE-0002.0002 (contexto de tenant) · FEATURE-0002.0003 (RBAC) |
| **User stories** | [US-0001](../user-stories/US-FEAT-0002.0001-0001-realm-client-keycloak.md) · [US-0002](../user-stories/US-FEAT-0002.0001-0002-autenticacao-oidc-backend.md) |
| **🔒 Travada por** | — (livre) |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Objetivo de negócio

Permitir que usuários autentiquem no CRM via OIDC (Keycloak auto-hospedado), estabelecendo a
identidade que é a base do contexto de tenant e do controle de acesso.

## 2. Escopo

### Entra
- Realm e client Keycloak para o Sociera.
- Autenticação das requisições do backend via OIDC (token JWT validado).
- Proteção das rotas de API contra acesso não autenticado.

### Fora (nesta feature)
- RBAC (papéis e permissões) → FEATURE-0002.0003.
- SSO unificado com os demais SaaS → Release 3 do portal.

## 3. Regras de negócio

| ID | Regra |
|---|---|
| BR-0001 | Toda rota de API exige token OIDC válido, exceto healthcheck. |
| BR-0002 | O tenant é sempre derivado do token autenticado — nunca de parâmetro do cliente. |

## 5. User stories desta feature

| ID | História | Critérios |
|---|---|---|
| [US-FEAT-0002.0001-0001](../user-stories/US-FEAT-0002.0001-0001-realm-client-keycloak.md) | Configurar realm e client Keycloak | 2 AC |
| [US-FEAT-0002.0001-0002](../user-stories/US-FEAT-0002.0001-0002-autenticacao-oidc-backend.md) | Autenticar via OIDC no backend | 3 AC |

## 7. Critérios de aceite da feature (DoD)

- [ ] Requisição sem token é rejeitada (401); com token válido, autenticada.
- [ ] Realm/client Keycloak versionados (script/terraform) e reprodutíveis.

## 8. Decisões pendentes deste documento

1. `[ ]` Nome exato do realm e escopos de client — no refinamento técnico (dono: Romeu Augusto).
