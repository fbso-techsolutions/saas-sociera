# ✨ FEATURE-0009.0003 — Mapeamento de campos e origem

| Campo | Valor |
|---|---|
| **Projeto** | Sociera by FBSO · PRJ-CORP-2026-0000-CRM |
| **Épico** | [EPIC-0009 — Ingestão de Leads do Portal](../epicos/EPIC-0009-ingestao-leads-portal.md) |
| **B-REQ dona** | B-REQ-06 |
| **Prioridade** | Onda 1-Must (MVP) |
| **Requisitos** | B-REQ-06 |
| **Depende de** | FEATURE-0009.0002 (endpoint) |
| **Entra depois** | — |
| **User stories** | — (a criar — Sprint 2) |
| **🔒 Travada por** | — (livre) |
| **Status** | 📝 Rascunho (2026-11-26) |

## 1. Objetivo de negócio

Mapear os campos do formulário do portal para o schema do lead, preservando a origem de aquisição
(`source`/`medium`/`campaign`) no registro.

## 2. Escopo

### Entra
- Mapeamento 1:1 dos campos (contato, produto/interesse, origem).
- Persistência da origem de aquisição no lead.

### Fora (nesta feature)
- Analytics/GA4 → portal-fbso (FEATURE-0006.0001).

## 7. Critérios de aceite da feature (DoD)

- [ ] Lead chega com `source`/`medium`/`campaign` preenchidos e status correto.

## 8. Decisões pendentes deste documento

1. `[ ]` Valores canônicos de origem — com PM/PO + Comercial.
