# Core Architectural Knowledge Reference

## Quality Attributes

| Attribute | Key Metrics | Considerations |
|-----------|-------------|----------------|
| Performance | Latency (p50/p95/p99), throughput, capacity | Caching, async processing, query optimization |
| Scalability | Horizontal/vertical scaling, elasticity | Stateless design, partition strategies |
| Availability | SLO targets, failure domains, redundancy | Multi-AZ, circuit breakers, graceful degradation |
| Security | Zero trust, defense in depth, blast radius | AuthN/AuthZ, encryption, audit logging |
| Modifiability | Coupling, cohesion, testability | Clean boundaries, dependency inversion |
| Deployability | CI/CD compatibility, rollback capability | Blue-green, canary, feature flags |
| Cost/FinOps | Right-sizing, reserved vs on-demand, data transfer | Spot instances, auto-scaling policies |
| Observability | Metrics, logs, traces (OpenTelemetry) | SLI/SLO/SLA, alerting, dashboards |

## Trade-off Pairs

| Trade-off | Description |
|-----------|-------------|
| Consistency ↔ Availability | CAP theorem - choose 2 of 3 |
| Latency ↔ Consistency | PACELC - when partitioned (C/A), else (L/C) |
| Flexibility ↔ Performance | Abstractions add overhead |
| Autonomy ↔ Governance | Team independence vs organizational standards |
| Speed ↔ Safety | Fast iteration vs rigorous validation |
| Cost ↔ Performance | Resource optimization vs capability |
| Simplicity ↔ Scalability | Monolith ease vs distributed complexity |

## Architectural Patterns

| Pattern | When to Use | Watch Out For |
|---------|-------------|---------------|
| Event Sourcing | Audit trails, temporal queries, replay | Complexity, eventual consistency |
| CQRS | Divergent read/write patterns | Synchronization complexity |
| Saga (Orchestration) | Complex workflows, visibility needed | Orchestrator bottleneck |
| Saga (Choreography) | Loose coupling, simple flows | Hard to understand globally |
| Outbox | Reliable event publishing | Additional infrastructure |
| Strangler Fig | Legacy migration | Long transition period |
| Anti-Corruption Layer | External integration isolation | Translation overhead |
| Circuit Breaker | Resilience to failures | Tuning complexity |
| Bulkhead | Isolation of failures | Resource overhead |
| Backend for Frontend | Client-specific APIs | Duplication risk |
| API Gateway | Cross-cutting concerns | Single point of failure |

## Architectural Styles

| Style | When Appropriate | Key Characteristics |
|-------|------------------|---------------------|
| Monolithic | Small team, unclear domains, discovery phase | Single deployment, shared database |
| Modular Monolith | Clear bounded contexts, single deployment preferred | Module boundaries, prepared for extraction |
| Microservices | Team autonomy, independent scaling, polyglot | Service per bounded context, distributed |
| Event-Driven | Temporal decoupling, audit needs, choreography | Async messaging, eventual consistency |
| Cell-Based | Blast radius isolation, regional/regulatory boundaries | Independent cells, routing layer |
| Serverless | Variable load, cost optimization, rapid iteration | Functions, managed services |

## DDD Quick Reference

**Strategic**: Bounded contexts, context mapping (ACL, Open Host, Shared Kernel, Customer-Supplier, Conformist)
**Tactical**: Aggregates, entities, value objects, domain events, repositories, domain services
**Distillation**: Core domain (competitive advantage), supporting (necessary), generic (commodity)

## 12-Factor Principles

Codebase | Dependencies | Config | Backing Services | Build/Release/Run | Processes | Port Binding | Concurrency | Disposability | Dev/Prod Parity | Logs | Admin Processes

**Beyond 12-Factor**: API-first, telemetry, auth/authz, scheduling, cost awareness
