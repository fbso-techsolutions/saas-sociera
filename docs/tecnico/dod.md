# ✅ Definition of Done (DoD) — Sociera

> **Padrão compartilhado de qualidade.** Um item (story · enabler · task) só está
> **"Concluído"/`✅ Entregue`** quando todos os critérios **aplicáveis** estão marcados, com
> **evidência real** (PR/commit/deploy), não intenção. Referenciado pelo
> [sprint doc](../../projects/PRJ-CORP-2026-0000-CRM/prj-produto/sprints/sprint-0001-fundacao-multi-tenancy.md) §5.2.

## 1. DoD comum (aplica a todo item)

| # | Critério | Obrigatório? |
|---|---|---|
| D1 | Código segue os padrões da org (`coding-standards-react.md` · convenções de commit/branch) | Sim |
| D2 | Testes do item passam localmente e no CI | Sim |
| D3 | **PR aberto, revisado e aprovado** (autor + Tech Lead) | Sim |
| D4 | **CI verde** (`lint · format:check · typecheck · test · build`) | Sim |
| D5 | **Evidência real** anexada (link do PR/commit/deploy) no board | Sim |
| D6 | Sem segredos no código; baseline de segurança respeitado ([SECURITY.md](https://github.com/fbso-techsolutions/platform-standards/blob/main/standards/security/SECURITY.md)) | Sim |

## 2. DoD por tipo

| Tipo | Critério adicional |
|---|---|
| **User Story** | Critérios de aceite (Gherkin) validados; cenário feliz + alternativo passando |
| **Enabler** | Critério de saída **binário** provado + "habilita" rastreável (guia §2) |
| **Task** | Critério de saída (§3) provado + runbook (§4) quando aplicável |
| **Qualquer item que manipule dados** | **Teste de isolamento cross-tenant** passando — meta incidente zero ([ADR-002](arquitetura/adrs/adr-002-multi-tenant-duas-camadas.md)) |

## 3. Regras de ouro

1. **Sem evidência, o `[x]` é intenção** — só marca "Concluído" com artefato verificável (PR/teste/deploy).
2. **`✅ Entregue` no backlog exige DoD + evidência** — nunca "feito de cabeça".
3. **DoD não substitui o AC** — o AC é por história (Gherkin); o DoD é o padrão compartilhado de "pronto".
