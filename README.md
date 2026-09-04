# system-design-notes

Architecture notes, three times a week — one concept, one diagram, one scalability problem solved.

## What this is

A public log of system design decisions, trade-offs, and patterns. Each entry is a short, practical note you can reference in interviews, design reviews, or when building production systems.

**Every Monday, Wednesday, and Friday:**
- One markdown note
- One diagram
- One real scalability problem solved

*(Entries through 2026-08-20 were published daily.)*

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
  YYYY-MM-DD-topic-slug.md    # note + embedded diagram
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
| 2026-07-07 | [Load balancing strategies](notes/2026-07-07-load-balancing-strategies.md) | Pick the right algorithm — round robin, least connections, or consistent hash — for your workload shape |
| 2026-07-08 | [Webhook signature verification](notes/2026-07-08-webhook-signature-verification.md) | Verify HMAC signatures on inbound webhooks before they trigger payments or state changes |
| 2026-07-09 | [Change data capture with Debezium](notes/2026-07-09-change-data-capture-debezium.md) | Stream every database change from the WAL to sync caches and search indexes without dual-writes |
| 2026-07-10 | [API versioning strategies](notes/2026-07-10-api-versioning-strategies.md) | Evolve APIs without breaking installed clients using adapters over a shared core and sunset headers |
| 2026-07-11 | [Full-text search: PostgreSQL vs Elasticsearch](notes/2026-07-11-full-text-search-postgres-elasticsearch.md) | Ship search with tsvector and pg_trgm first — know the real crossover point to Elasticsearch |
| 2026-07-12 | [Hot partitions and the celebrity problem](notes/2026-07-12-hot-partitions-celebrity-problem.md) | Fix skewed access with key salting, caching, and hybrid fan-out — re-sharding can't save you |
| 2026-07-13 | [Batch vs stream processing](notes/2026-07-13-batch-vs-stream-processing.md) | Choose per pipeline: seconds-level reactions need streams, auditable numbers need batch |
| 2026-07-14 | [JWT vs server-side sessions](notes/2026-07-14-jwt-vs-sessions.md) | Combine short-lived JWTs with rotating refresh tokens for local verification and bounded revocation |
| 2026-07-15 | [Materialized views](notes/2026-07-15-materialized-views.md) | Precompute expensive aggregations into indexable snapshots refreshed on your freshness budget |
| 2026-07-16 | [gRPC vs REST vs GraphQL](notes/2026-07-16-grpc-rest-graphql.md) | Match each API style to its boundary — gRPC inside, REST outside, GraphQL for client aggregation |
| 2026-07-17 | [Distributed ID generation](notes/2026-07-17-distributed-id-generation.md) | Generate unique, time-sortable IDs on any node — UUIDv7 by default, Snowflake when 64 bits matter |
| 2026-07-18 | [N+1 queries and DataLoader](notes/2026-07-18-n-plus-one-queries-dataloader.md) | Collapse one-query-per-item explosions with joins, IN batching, or transparent DataLoader batching |
| 2026-07-19 | [SLIs, SLOs, and error budgets](notes/2026-07-19-sli-slo-error-budgets.md) | Define reliability in numbers and let the error budget arbitrate ship-vs-fix decisions |
| 2026-07-20 | [Exactly-once delivery and deduplication](notes/2026-07-20-exactly-once-delivery.md) | Build exactly-once effects on at-least-once delivery with transactional dedup |
| 2026-07-21 | [Time-series data storage](notes/2026-07-21-time-series-data-storage.md) | Chunk by time, compress old data, and downsample — retention by dropping chunks, not deleting rows |
| 2026-07-22 | [Secrets management](notes/2026-07-22-secrets-management.md) | Replace static credentials with dynamic, short-lived secrets tied to platform identity |
| 2026-07-23 | [Serverless cold starts](notes/2026-07-23-serverless-cold-starts.md) | Cut cold-start latency with smaller bundles, lazy init, and surgical provisioned concurrency |
| 2026-07-24 | [Multi-tenancy data isolation models](notes/2026-07-24-multi-tenancy-isolation-models.md) | Choose pooled with RLS, schema-per-tenant, or silo databases — and tier them by what customers pay for |
| 2026-07-25 | [Geospatial indexing](notes/2026-07-25-geospatial-indexing.md) | Answer "what's within 5km" with R-trees, geohashes, or H3 cells — B-trees on lat/lng can't |
| 2026-07-26 | [Search autocomplete at scale](notes/2026-07-26-search-autocomplete.md) | Precompute top-K completions per prefix so every keystroke is one O(1) lookup |
| 2026-07-27 | [Distributed cron and job scheduling](notes/2026-07-27-distributed-cron-job-scheduling.md) | Split tick from work: elect one scheduler, enqueue jobs, dedupe workers on run keys |
| 2026-07-28 | [Vector search and embeddings](notes/2026-07-28-vector-search-embeddings.md) | Serve semantic search with HNSW indexes, hybrid BM25 merging, and reranking |
| 2026-07-29 | [Chaos engineering](notes/2026-07-29-chaos-engineering.md) | Test failovers and retries on your schedule with hypothesis-driven fault injection |
| 2026-07-30 | [Data deletion at scale (GDPR)](notes/2026-07-30-gdpr-deletion-at-scale.md) | Orchestrate erasure across every store and third party — crypto-shredding solves the backup problem |
| 2026-07-31 | [Scaling Redis: Cluster and Sentinel](notes/2026-07-31-redis-cluster-scaling.md) | Pick replicas, Sentinel, or Cluster by actual bottleneck — and audit multi-key ops before sharding |
| 2026-08-01 | [Implementing the strangler fig](notes/2026-08-01-strangler-fig-implementation.md) | The execution playbook: facade routing, shadow-mode parity proof, CDC data phases, automated cutover |
| 2026-08-02 | [OAuth 2.0 and OIDC flows in practice](notes/2026-08-02-oauth2-oidc-flows.md) | One right flow per client type — PKCE everywhere, and the token validation checks that actually break |
| 2026-08-03 | [Double-entry ledgers for payments](notes/2026-08-03-double-entry-ledgers.md) | Record immutable money movements, derive balances, and make every discrepancy a queryable diff |
| 2026-08-04 | [Notification fan-out at scale](notes/2026-08-04-notification-fanout.md) | Paginated fan-out, preference filtering, priority-isolated queues, and the feedback loops that protect deliverability |
| 2026-08-05 | [PostgreSQL VACUUM and bloat](notes/2026-08-05-postgres-vacuum-bloat.md) | Tune autovacuum per hot table, bound long transactions, and watch the wraparound clock |
| 2026-08-06 | [Kafka consumer group rebalancing](notes/2026-08-06-kafka-consumer-rebalancing.md) | Cooperative sticky assignment and static membership turn deploy-time rebalance storms into non-events |
| 2026-08-07 | [URL shortener design](notes/2026-08-07-url-shortener-design.md) | Scrambled snowflake codes, cache-everything redirects, async analytics — and the abuse layer interviews skip |
| 2026-08-08 | [Scaling WebSockets](notes/2026-08-08-websocket-scaling.md) | Split connection gateways from business logic, route via pub/sub, and track presence with TTL leases |
| 2026-08-09 | [Resumable large file uploads](notes/2026-08-09-resumable-file-uploads.md) | Multipart presigned uploads direct to storage — resume from the last confirmed part, never restart from zero |
| 2026-08-10 | [HTTP caching: Cache-Control and ETags](notes/2026-08-10-http-caching-etags.md) | Explicit cache headers on every response, cheap-version ETags for 304s, and surrogate-key purging at the CDN |
| 2026-08-11 | [Metrics cardinality](notes/2026-08-11-metrics-cardinality.md) | Every label combination is a stored series — bounded labels in metrics, IDs in traces, quotas as guardrails |
| 2026-08-12 | [Kubernetes requests, limits, and OOMKills](notes/2026-08-12-kubernetes-requests-limits.md) | Requests place and protect pods, limits throttle or kill them — size both from measured usage, not vibes |
| 2026-08-13 | [Queue-based autoscaling with KEDA](notes/2026-08-13-queue-based-autoscaling-keda.md) | Scale workers on queue depth, not CPU — with scale-to-zero and drain-safe scale-in |
| 2026-08-14 | [A/B testing infrastructure](notes/2026-08-14-ab-testing-experimentation.md) | Deterministic hash assignment, exposure logging, SRM checks, and the statistics that stop you shipping noise |
| 2026-08-15 | [CRDTs and collaborative editing](notes/2026-08-15-crdts-collaborative-editing.md) | Character identity instead of position makes concurrent edits merge by construction — via Yjs, never hand-rolled |
| 2026-08-16 | [Email deliverability](notes/2026-08-16-email-deliverability.md) | SPF, DKIM, and DMARC alignment plus stream separation and warm-up — inbox placement is reputation management |
| 2026-08-17 | [Audit logging](notes/2026-08-17-audit-logging.md) | Outbox-captured, append-only, tamper-evident records of who did what — a compliance feature, not a log config |
| 2026-08-18 | [Soft deletes and archival](notes/2026-08-18-soft-deletes-archival.md) | Soft delete with partial indexes for undo, then a scheduled ladder: archive out of live tables, erase on the compliance clock |
| 2026-08-19 | [Log aggregation pipelines](notes/2026-08-19-log-aggregation-pipelines.md) | stdout + DaemonSet agents, a buffer tier for storms, and the index-labels-vs-index-everything cost decision |
| 2026-08-20 | [Database failover and connection resilience](notes/2026-08-20-database-failover.md) | The promotion is fast; your pods are slow — proxy layers, timeouts, fencing, and drills close the gap |
| 2026-08-21 | [News feed design](notes/2026-08-21-news-feed-design.md) | Hybrid fan-out: push for normal users, pull-merge for celebrities, and skip the inactive entirely |
| 2026-08-24 | [Chat message storage at scale](notes/2026-08-24-chat-message-storage.md) | Partition by (channel, time bucket) with snowflake clustering — the query becomes the disk layout |
| 2026-08-26 | [Video streaming pipeline](notes/2026-08-26-video-streaming-pipeline.md) | Transcode once into an adaptive ladder, chunk into segments, let the player pick quality per segment |
| 2026-08-28 | [Probabilistic data structures](notes/2026-08-28-probabilistic-data-structures.md) | HyperLogLog, count-min sketch, and Top-K — bounded-error answers in kilobytes instead of gigabytes |
| 2026-08-31 | [Event schema evolution and registries](notes/2026-08-31-schema-evolution-registry.md) | Stored events live forever — registries with transitive compatibility move the break from 3am to CI |
| 2026-09-02 | [Service discovery](notes/2026-09-02-service-discovery.md) | Registration via readiness probes, resolution via DNS/VIP or client-side LB — and stale-beats-empty when the registry hiccups |
| 2026-09-04 | [Recommendation system architecture](notes/2026-09-04-recommendation-systems.md) | The funnel: cheap retrieval to hundreds, learned ranking, business rules last — with a feature store killing train/serve skew |

---

*Building in public. One note at a time.*
