# 🗂️ Produto: o QUÊ

Nível **produto** da Sociera: o que o produto faz, independentemente de projeto.

## Catálogo de capacidades

| Módulo | Responsabilidades | Prioridade |
|---|---|---|
| Tenants e configurações | Organizações clientes, contexto de isolamento | MVP — fundacional |
| Identidade e acesso | Autenticação (OIDC), usuários, papéis, permissões (RBAC) | MVP — fundacional |
| Parties | Cadastro unificado de PF/PJ | MVP |
| Party Roles | Papéis que uma pessoa/organização exerce | MVP |
| Relacionamentos | Vínculos entre parties e papéis | MVP |
| Pipelines | Funis e etapas configuráveis | MVP |
| Deals | Oportunidades, etapa, valor, moeda, vínculo com Party | MVP |
| Tarefas e interações | Atividades e histórico de relacionamento | MVP |
| **Ingestão de leads** | Recebimento de leads do portal (contrato de solução) | MVP |
| Auditoria | Registro rastreável de operações | MVP — fundacional |
| Atendimento / Tickets | Filas, tickets, responsáveis, histórico | Fase 2 |
| SLAs e escalonamento | Prazos e escalonamentos | Fase 2 |
| Base de conhecimento | Conteúdo de apoio ao atendimento | Fase 2 |
| Eventos e Webhooks | Publicação/consumo de eventos de integração | Fase 2 |
| Integrações Cross-SaaS | Comunicação com Educatio/Fiscalia/Mercator/Materiae | Fase 3 |
| Templates de indústria | Configurações pré-definidas por segmento | Pós-tração |
| IA | Qualificação, resumo e enriquecimento assistido | Evolução |

## Limites do MVP (Trilha A — simples)

O MVP permite à FBSO Tech Services operar o comercial básico. Deve priorizar: isolamento por
tenant, cadastro de pessoas/organizações, papéis e relacionamentos, pipeline + oportunidades em
Kanban, tarefas/interações, auditoria, **ingestão de leads do portal** e API documentada.

**Não incluir no MVP:** Kestra, mensageria dedicada, mobile, múltiplos templates setoriais,
automações sofisticadas e IA não necessária à validação.

> Fila única de backlog e fatiamento: [projects/PRJ-CORP-2026-0000-CRM/](../../projects/PRJ-CORP-2026-0000-CRM).
