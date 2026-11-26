# ADR-004 - Mensageria MVP: Outbox + scheduler + webhook (sem broker)

| Campo | Conteúdo |
|---|---|
| **Data / Status** | 2026-11-26 · ✅ **Decidida** |
| **Contexto** | O plano deixou a mensageria em aberto (Redis Streams / RabbitMQ / Kafka). Introduzir um broker dedicado no MVP adiciona custo operacional sem volume que o justifique. |
| **Decisão** | Começar apenas com a tabela **`outbox_events`** no PostgreSQL + um **scheduler no Quarkus** que relê os eventos pendentes e dispara **webhooks HTTP** (para o Kestra e futuros consumidores). Introduzir RabbitMQ/Kafka **somente quando o volume de eventos exigir**. |
| **Justificativa** | Preserva o padrão Transactional Outbox (sem perda/dual-write) com custo mínimo; webhooks HTTP atendem o volume do MVP. |
| **Consequências** | Relay por scheduler/polling (latência aceitável no MVP); consumidores idempotentes (entrega *at-least-once*); mudança para broker só por gatilho de volume, registrada em novo ADR. |
| **Alternativas rejeitadas** | **Kafka/RabbitMQ no MVP**: custo operacional antecipado; **Redis Streams**: mais um componente sem necessidade no início; **publicar evento direto da transação**: dual-write e risco de perda. |
| **Rastreio** | [arquitetura §5](../README.md) · EPIC-0012 (prj-produto) · `platform-standards/standards/architecture/guardrail-eventos-outbox.md` |
| **Assinatura** | Tech lead (Romeu Augusto) + Arquiteto de Soluções (Ricardo David) · 2026-11-26 |
