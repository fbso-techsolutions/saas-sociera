# 🎯 Visão — Sociera by FBSO

> Sociera — CRM próprio (simples) da FBSO Technology Solutions. Fonte de origem: `.temporaria/ideias/crm/`
> (`PLANO-IMPLEMENTACAO-FBSO-CRM.md` · `FBSO CRM - IDEIAS - 0001.md`), conformado.

## 1. O que é

Sociera — produto SaaS multi-tenant (CRM). Núcleo de relacionamento (pessoas,
organizações e papéis), funil comercial e, em evolução, atendimento (tickets/SLA). Primeira
validação: operação comercial da **FBSO Tech Services**; em seguida, hub de relacionamento e
integração dos SaaS **Educatio**, **Fiscalia**, **Mercator** e **Materiae**.

## 2. Visão

Plataforma CRM flexível e extensível que centraliza o relacionamento com pessoas e organizações,
apoia os processos comerciais e de atendimento da FBSO e conecta progressivamente os sistemas do
ecossistema FBSO.

## 3. Objetivos do produto

1. Apoiar a gestão comercial B2B da FBSO Tech Services.
2. Organizar empresas, pessoas, contatos, papéis e relacionamentos em cadastro consistente.
3. Gerir funis, oportunidades, tarefas e interações comerciais.
4. Apoiar pós-venda, sustentação e atendimento por meio de tickets e SLAs (evolução).
5. Disponibilizar APIs e eventos padronizados para integração com os SaaS da FBSO (evolução).
6. Permitir automações e orquestrações de processos com Kestra (evolução).
7. Criar base tecnológica apta a evoluir para oferta SaaS B2B a outros clientes (pós-tração).

## 4. Princípios orientadores

- Núcleo genérico, extensões específicas ("One Core, Multiple Verticals").
- API-first e integração por contratos explícitos.
- Multi-tenancy e segurança desde a primeira linha.
- Configuração antes de customização de código, quando viável.
- Eventos versionados e rastreáveis.
- Auditoria das operações relevantes.
- Entrega incremental e validação com usuários reais.
- Frameworks como referência, não como implementação integral obrigatória.

## 5. Posicionamento e estratégia de adoção

**Tenant inicial (dogfooding):** FBSO Tech Services — prospecção, qualificação, oportunidades de
consultoria/engenharia, propostas, contratos de sustentação e atendimento.

**Evolução para o ecossistema:**

| Produto / operação | Exemplos de papéis e processos |
|---|---|
| FBSO Tech Services | Lead, cliente, parceiro; oportunidades de consultoria, alocação de squads |
| Educatio | Aluno, responsável, instituição; matrícula/rematrícula |
| Fiscalia | Empresa cliente, contador; onboarding fiscal e obrigações |
| Mercator | Consumidor, fornecedor; histórico de compras e fidelidade |
| Materiae | Gerador de resíduo, reciclador; ciclo de vida do ativo |

> Fronteira: o CRM é o **relacionamento/funil da FBSO**; o Mercator é **varejo/POS vendido a
> lojistas**. Não se sobrepõem.

## 6. Frameworks de referência (seletivos)

| Referência | Aplicação |
|---|---|
| FIBO, ACORD, ARTS, HL7/FHIR | Inspiração para o Party Model e extensões setoriais |
| APQC PCF | Organização de processos de mercado, vendas e pós-venda |
| ITIL 4 | Atendimento, tickets, filas, SLAs, escalonamento |
| TM Forum ODA, BIAN | Referências de domínio de serviço e arquitetura modular |
| Open Finance | Referência de segurança OAuth 2.0 / OIDC |
| ISO 20022 | Semântica de eventos JSON tipados/versionados (não o XML) |
| TOGAF, COBIT, Zachman | Governança, segregação, auditoria e checklist de desenho |

> **Diretriz:** usar conceitos que resolvam necessidades concretas — não implementar frameworks
> integralmente nem produzir documentação extensa antes da validação.
