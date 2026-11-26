# ✨ FEATURE-0002.0004 — Segregação e testes multi-tenant

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Épico** | [EPIC-0002 — Identidade e Multi-tenancy](../epicos/EPIC-0002-identidade-multi-tenancy.md) |
| **B-REQ dona** | B-REQ-01 |
| **Prioridade** | Onda 1-Must (MVP) |
| **Requisitos** | B-REQ-01 |
| **Depende de** | FEATURE-0002.0002 (contexto de tenant) |
| **Entra depois** | — |
| **User stories** | [US-0004](../user-stories/US-FEAT-0002.0004-0004-rls-isolamento.md) |
| **🔒 Travada por** | — (livre) |
| **Status** | ✅ Revisado (2026-11-26) |

## 1. Objetivo de negócio

Adicionar a **segunda camada** de isolamento no banco (Row-Level Security) e provar, por teste
automatizado, que um tenant não acessa dados de outro — cumprindo o critério de bloqueio do
[ADR-002](../../../../docs/tecnico/arquitetura/adrs/adr-002-multi-tenant-duas-camadas.md).

## 2. Escopo

### Entra
- Políticas de RLS no PostgreSQL (`SET LOCAL app.current_tenant = '<uuid>'` na conexão).
- Teste automatizado de tentativa de acesso entre tenants.

### Fora (nesta feature)
- RBAC → FEATURE-0002.0003.
- Onboarding de tenants → Fase 4.

## 3. Regras de negócio

| ID | Regra |
|---|---|
| BR-0005 | Sem `app.current_tenant` definido, o banco nega acesso (fail-closed). |

## 5. User stories desta feature

| ID | História | Critérios |
|---|---|---|
| [US-FEAT-0002.0004-0004](../user-stories/US-FEAT-0002.0004-0004-rls-isolamento.md) | Aplicar RLS e testar isolamento entre tenants | 3 AC |

## 7. Critérios de aceite da feature (DoD)

- [ ] Teste automatizado prova que tenant A não lê/escreve dados do tenant B (meta: incidente zero).

## 8. Decisões pendentes deste documento

1. `[ ]` Papel de banco usado pela aplicação — com o Arquiteto (Ricardo David).
