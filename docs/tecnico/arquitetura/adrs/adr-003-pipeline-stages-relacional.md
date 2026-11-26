# ADR-003 - Etapas de pipeline em tabela relacional (não JSONB)

| Campo | Conteúdo |
|---|---|
| **Data / Status** | 2026-11-26 · ✅ **Decidida** (proposta do PO; assinaturas a coletar — PENDENCY-0006) |
| **Contexto** | O plano (§7.3/§16) alertou que guardar etapas como array JSON dentro de `pipelines` dificulta chaves estrangeiras, relatórios de conversão por etapa e histórico de movimentação. |
| **Decisão** | Modelar etapas em tabela própria **`pipeline_stages`** (`id`, `tenant_id`, `pipeline_id`, `name`, `position`, `is_won`, `is_lost`) e histórico em **`deal_stage_history`** (registra quanto tempo cada oportunidade ficou em cada fase). |
| **Justificativa** | Permite FK, relatório de conversão por etapa (funil) e auditoria de tempo em cada fase; preserva integridade e histórico de transições. |
| **Consequências** | `pipeline_stages` e `deal_stage_history` entram no modelo de domínio; JSONB fica restrito a atributos realmente variáveis (regra estrutural 5). |
| **Alternativas rejeitadas** | **Etapas como JSONB no `pipelines`**: flexível, mas quebra FK/conversão/histórico. |
| **Rastreio** | [domain.md](../../domain.md) · EPIC-0005 · EPIC-0006 (prj-produto) |
| **Assinatura** | — (a assinar — squad a preencher, PENDENCY-0006) |
