# system-design-notes

Daily architecture repository — one concept, one diagram, one scalability problem solved.

## What this is

A public log of system design decisions, trade-offs, and patterns. Each entry is a short, practical note you can reference in interviews, design reviews, or when building production systems.

**Every day:**
- One markdown note
- One diagram
- One real scalability problem solved

## Topics

- Redis queue architecture
- Webhook retry systems
- Kubernetes scaling
- PostgreSQL indexing
- Event-driven systems
- AI agent orchestration
- Caching, sharding, rate limiting, and more

## Structure

```
notes/
  YYYY-MM-DD-topic-slug.md    # daily note + embedded diagram
diagrams/
  YYYY-MM-DD-topic-slug.mmd   # source diagram (Mermaid)
```

## How to read

Browse [`notes/`](notes/) chronologically, or search by topic. Each note follows the same template: problem → constraints → architecture → trade-offs → when to use.

## Index

| Date | Topic | Problem solved |
|------|-------|----------------|
| 2026-05-21 | [Redis queue architecture](notes/2026-05-21-redis-queue-architecture.md) | Decouple producers from slow consumers without losing work |
| 2026-05-22 | [Webhook retry systems](notes/2026-05-22-webhook-retry-systems.md) | Deliver webhooks reliably when receivers are down or return 5xx |
| 2026-05-23 | [Kubernetes HPA scaling](notes/2026-05-23-kubernetes-hpa-scaling.md) | Scale pod replicas automatically when CPU, memory, or custom metrics cross thresholds |
| 2026-05-24 | [PostgreSQL indexing strategies](notes/2026-05-24-postgresql-indexing-strategies.md) | Cut read latency on large tables without bloating writes and storage |
| 2026-05-25 | [Transactional outbox pattern](notes/2026-05-25-transactional-outbox-pattern.md) | Publish domain events atomically with database writes — no dual-write bugs |
| 2026-05-26 | [AI agent orchestration](notes/2026-05-26-ai-agent-orchestration.md) | Route complex tasks across specialized agents with tools, memory, and fallbacks |
| 2026-05-27 | [Cache-aside with Redis](notes/2026-05-27-cache-aside-redis.md) | Serve hot reads from memory without sacrificing PostgreSQL as the source of truth |
| 2026-05-28 | [Database sharding by tenant](notes/2026-05-28-database-sharding-by-tenant.md) | Isolate noisy tenants and scale writes beyond a single PostgreSQL instance |
| 2026-05-29 | [Token bucket rate limiting](notes/2026-05-29-token-bucket-rate-limiting.md) | Protect APIs from abuse and traffic spikes with smooth, burst-tolerant limits per client |
| 2026-05-30 | [CQRS read models](notes/2026-05-30-cqrs-read-models.md) | Optimize read paths separately when writes and queries have different shapes and scale |
| 2026-05-31 | [Circuit breaker for downstream calls](notes/2026-05-31-circuit-breaker-downstream-calls.md) | Fail fast when dependencies are unhealthy instead of cascading timeouts |
| 2026-06-01 | [Saga pattern for distributed transactions](notes/2026-06-01-saga-distributed-transactions.md) | Coordinate multi-service workflows with compensating actions instead of distributed 2PC |
| 2026-06-02 | [Idempotency keys for HTTP APIs](notes/2026-06-02-idempotency-keys-api.md) | Make POST/PUT safe to retry so network blips never double-charge or duplicate orders |
| 2026-06-03 | [Dead letter queues](notes/2026-06-03-dead-letter-queues.md) | Isolate poison messages so the main queue keeps draining healthy work |
| 2026-06-04 | [API gateway pattern](notes/2026-06-04-api-gateway-pattern.md) | Centralize auth, rate limits, and routing at the edge so backends stay domain-focused |
| 2026-06-06 | [Connection pooling with PgBouncer](notes/2026-06-06-connection-pooling-pgbouncer.md) | Multiplex thousands of app connections without exhausting PostgreSQL max_connections |
| 2026-06-07 | [Bloom filter for cache penetration](notes/2026-06-07-bloom-filter-cache-penetration.md) | Block guaranteed-miss lookups before bots hammer PostgreSQL with random IDs |
| 2026-06-08 | [Backpressure and graceful degradation](notes/2026-06-08-backpressure-graceful-degradation.md) | Shed work deliberately when load exceeds capacity instead of cascading failure |

---

*Building in public. One note at a time.*
