# 🧬 Modelo de domínio — Party Model

> Núcleo agnóstico: evita cadastros isolados e rígidos por tipo de participante. Fonte:
> `.temporaria/ideias/crm/` (modelo SQL é referência inicial, não modelo físico pronto).
> Refinado a partir das sugestões ao plano (pipeline em tabela própria, atividades, RLS).

## Entidades iniciais

| Entidade | Finalidade |
|---|---|
| Tenant | Organização/cliente do SaaS e contexto de segregação |
| Party | Pessoa física ou organização (party_type: `INDIVIDUAL` / `ORGANIZATION`) |
| PartyRole | Papel exercido por uma Party (`LEAD`, `CUSTOMER`, `STUDENT`, `SUPPLIER`…) |
| PartyRelationship | Relacionamento entre Parties |
| Pipeline | Funil comercial de um tenant |
| PipelineStage | Etapa de um pipeline (`name`, `position`, `is_won`, `is_lost`) |
| Deal | Oportunidade vinculada a Party + Pipeline (etapa, valor, moeda) |
| DealStageHistory | Histórico de movimentação do Deal entre etapas (tempo em cada fase) |

## Entidades complementares (detalhar no MVP)

- `User` e membership do usuário no tenant.
- `Activity` (tarefas e interações do relacionamento).
- `AuditLog`.
- Configurações e permissões.
- `OutboxEvent`.

## Decisões de modelagem (fechadas — ADRs)

1. **Etapas de pipeline em tabela própria** (`pipeline_stages`) — não JSONB. Preserva FK,
   relatório de conversão por etapa e histórico. `deal_stage_history` registra o tempo em cada
   fase. Ver [ADR-003](arquitetura/adrs/adr-003-pipeline-stages-relacional.md).
2. **Atividades** consolidam tarefas e interações (`activities`).

## Regras estruturais

1. Dados de negócio sempre associados ao tenant correspondente.
2. O tenant vem do **contexto autenticado** — nunca confiar em `tenant_id` enviado pelo cliente.
3. Restrições/relacionamentos impedem vínculos cruzados entre tenants.
4. Uma mesma Party pode ser lead, cliente e parceiro em contextos adequados (papéis).
5. JSONB para atributos variáveis — **não** substitui colunas relacionais quando há integridade,
   busca frequente ou regra transacional.
6. Mudança de etapa de pipeline gera registro em `deal_stage_history`.
7. Dados pessoais/fiscais exigem controle de acesso, retenção e proteção (LGPD).

> Antes de implementar, detalhar: integridade por tenant, unicidade de identificadores fiscais,
> histórico, exclusão lógica/anonimização, índices e separação entre usuários globais da
> plataforma e usuários de cada tenant. Isolamento em duas camadas: ver
> [arquitetura](arquitetura/README.md).
