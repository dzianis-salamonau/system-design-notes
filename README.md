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

---

*Building in public. One note at a time.*
