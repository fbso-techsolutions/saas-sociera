# 🧬 Modelo de domínio — Party Model

> Núcleo agnóstico: evita cadastros isolados e rígidos por tipo de participante. Fonte:
> `.temporaria/ideias/crm/` (modelo SQL é referência inicial, não modelo físico pronto).

## Entidades iniciais

| Entidade | Finalidade |
|---|---|
| Tenant | Organização/cliente do SaaS e contexto de segregação |
| Party | Pessoa física ou organização (party_type: `INDIVIDUAL` / `ORGANIZATION`) |
| PartyRole | Papel exercido por uma Party (`LEAD`, `CUSTOMER`, `STUDENT`, `SUPPLIER`…) |
| Relationship | Relacionamento entre Parties |
| Pipeline | Funil comercial de um tenant (etapas configuráveis) |
| Deal | Oportunidade vinculada a Party + Pipeline (etapa, valor, moeda) |

## Entidades complementares (detalhar no MVP)

- `User` e membership do usuário no tenant.
- `Task` e `Interaction`.
- `AuditLog`.
- Configurações e permissões.
- `OutboxEvent`.

## Regras estruturais

1. Dados de negócio sempre associados ao tenant correspondente.
2. O tenant vem do **contexto autenticado** — nunca confiar em `tenant_id` enviado pelo cliente.
3. Restrições/relacionamentos impedem vínculos cruzados entre tenants.
4. Uma mesma Party pode ser lead, cliente e parceiro em contextos adequados (papéis).
5. JSONB para atributos variáveis — **não** substitui colunas relacionais quando há integridade,
   busca frequente ou regra transacional.
6. Etapas de pipeline configuráveis, com integridade e histórico de transições.
7. Dados pessoais/fiscais exigem controle de acesso, retenção e proteção (LGPD).

> Antes de implementar, detalhar: integridade por tenant, unicidade de identificadores fiscais,
> histórico, exclusão lógica/anonimização, índices, estratégia de RLS e separação entre usuários
> globais da plataforma e usuários de cada tenant.
