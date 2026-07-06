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
| 2026-06-05 | [Blue-green deployment](notes/2026-06-05-blue-green-deployment.md) | Cut over traffic between two environments for instant rollback and minimal downtime |
| 2026-06-06 | [Connection pooling with PgBouncer](notes/2026-06-06-connection-pooling-pgbouncer.md) | Multiplex thousands of app connections without exhausting PostgreSQL max_connections |
| 2026-06-07 | [Bloom filter for cache penetration](notes/2026-06-07-bloom-filter-cache-penetration.md) | Block guaranteed-miss lookups before bots hammer PostgreSQL with random IDs |
| 2026-06-08 | [Backpressure and graceful degradation](notes/2026-06-08-backpressure-graceful-degradation.md) | Shed work deliberately when load exceeds capacity instead of cascading failure |
| 2026-06-09 | [Strangler fig migration](notes/2026-06-09-strangler-fig-migration.md) | Incrementally replace a legacy monolith by routing traffic to new services |
| 2026-06-10 | [Distributed tracing with OpenTelemetry](notes/2026-06-10-distributed-tracing-opentelemetry.md) | Follow one request across services when logs alone can't explain p99 latency |
| 2026-06-11 | [Liveness and readiness probes](notes/2026-06-11-liveness-readiness-probes.md) | Tell Kubernetes when to restart a pod vs when to stop sending traffic |
| 2026-06-12 | [Feature flags for progressive delivery](notes/2026-06-12-feature-flags-progressive-delivery.md) | Ship code daily but expose new behavior to 1% of users first |
| 2026-06-13 | [Consistent hashing](notes/2026-06-13-consistent-hashing.md) | Add or remove cache nodes without remapping every key on the ring |
| 2026-06-14 | [Kafka partitions and ordering](notes/2026-06-14-kafka-partitions-ordering.md) | Guarantee event order per entity while scaling consumers across partitions |
| 2026-06-15 | [Read replicas and replication lag](notes/2026-06-15-read-replicas-replication-lag.md) | Offload read traffic to replicas without ignoring replication lag |
| 2026-06-16 | [Bulkhead pattern](notes/2026-06-16-bulkhead-pattern.md) | Isolate thread pools per dependency so one slow service can't exhaust all resources |
| 2026-06-17 | [CDN edge caching](notes/2026-06-17-cdn-edge-caching.md) | Serve static assets from PoPs near users to cut origin load and latency |
| 2026-06-18 | [Event sourcing](notes/2026-06-18-event-sourcing.md) | Store state as append-only domain events and rebuild any projection |
| 2026-06-19 | [Graceful shutdown](notes/2026-06-19-graceful-shutdown.md) | Drain in-flight requests before killing a pod during deploys and scale-down |
| 2026-06-20 | [Correlation IDs and structured logging](notes/2026-06-20-correlation-ids-structured-logging.md) | Tie every log line to one request ID for cross-service debugging |
| 2026-06-21 | [Write-through cache](notes/2026-06-21-write-through-cache.md) | Update cache and database together on writes for fresh reads |
| 2026-06-22 | [Cursor pagination](notes/2026-06-22-cursor-pagination.md) | Paginate large datasets with keyset cursors instead of slow OFFSET scans |
| 2026-06-23 | [Optimistic locking](notes/2026-06-23-optimistic-locking.md) | Prevent lost updates on concurrent writes using a version column instead of row locks |
| 2026-06-24 | [Service mesh and sidecar proxy](notes/2026-06-24-service-mesh-sidecar-proxy.md) | Add mTLS, retries, and telemetry to every service without touching app code |
| 2026-06-25 | [Multi-region active-active](notes/2026-06-25-multi-region-active-active.md) | Serve writes from multiple regions for global latency and automatic region failover |
| 2026-06-26 | [Long polling vs SSE vs WebSockets](notes/2026-06-26-long-polling-sse-websockets.md) | Pick the right real-time transport so you don't over-engineer one-way push |
| 2026-06-27 | [Two-phase commit](notes/2026-06-27-two-phase-commit.md) | Atomically commit a write across multiple databases with no partial success |
| 2026-06-28 | [Leader election and Raft](notes/2026-06-28-leader-election-raft.md) | Elect one authoritative node automatically so a cluster survives failures without manual intervention |
| 2026-06-29 | [Object vs block vs file storage](notes/2026-06-29-object-block-file-storage.md) | Pick the right storage primitive before you build to avoid performance ceilings and cost explosions |
| 2026-06-30 | [Distributed locking with Redis](notes/2026-06-30-distributed-locking-redis.md) | Coordinate exclusive access across processes using SET NX and a unique token for safe release |
| 2026-07-01 | [Thundering herd and request coalescing](notes/2026-07-01-thundering-herd-request-coalescing.md) | Collapse thousands of cache misses on the same key into one database query |
| 2026-07-02 | [Pub/Sub vs message queues](notes/2026-07-02-pubsub-vs-message-queues.md) | Fan-out events to many subscribers or buffer work for one consumer — pick the right primitive |
| 2026-07-03 | [Write-behind caching](notes/2026-07-03-write-behind-caching.md) | Acknowledge writes instantly by flushing to the database asynchronously in batches |
| 2026-07-04 | [Canary deployments](notes/2026-07-04-canary-deployments.md) | Route a small slice of real traffic to a new version before promoting to 100% |
| 2026-07-05 | [Zero-downtime database migrations](notes/2026-07-05-zero-downtime-database-migrations.md) | Rename columns and change types using expand/contract so old and new code coexist |
| 2026-07-06 | [Exponential backoff and jitter](notes/2026-07-06-exponential-backoff-jitter.md) | Retry transient failures with increasing delays and randomised spread to avoid retry storms |

---

*Building in public. One note at a time.*
