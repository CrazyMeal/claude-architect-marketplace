---
description: Design a component with DDD tactical patterns and integration considerations
argument-hint: <component-name> [context-file]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Component Design

Deep-dive into a specific component within a larger system.

## DDD Tactical Patterns to Consider

### Aggregate Design
- What is the consistency boundary?
- What invariants must be protected?
- What is the aggregate root?
- How large should the aggregate be? (Prefer smaller, load by ID)

### Domain Events
- What state transitions are significant to other bounded contexts?
- Event naming: past tense, business language
- Event schema evolution strategy

### Repository Pattern
- Persistence ignorance in domain layer
- Query capabilities vs pure aggregate retrieval
- Specification pattern for complex queries

### Domain Services
- Stateless operations that don't belong to a single entity
- Cross-aggregate operations
- External service coordination

## Integration Patterns

When this component talks to others:

### Synchronous
- **Request-Response**: Simple, but creates temporal coupling
- **API Gateway**: Cross-cutting concerns, routing, transformation
- **Service Mesh**: Observability, security, traffic management at infra level
- **Backend for Frontend (BFF)**: Client-specific aggregation

### Asynchronous
- **Event-Carried State Transfer**: Eventual consistency, reduced chattiness
- **Event Notification**: Light events, receiver queries for details
- **Event Sourcing**: Full audit, temporal queries, replay capability
- **CQRS**: Separate read/write models when query patterns diverge significantly

### Anti-Corruption Layer
- When integrating with legacy or external systems
- Translation between models
- Protecting your domain model from external pollution

## Resilience Patterns

- **Circuit Breaker**: Fail fast, give downstream time to recover
- **Bulkhead**: Isolate failures, prevent cascade
- **Retry with backoff**: Transient failure handling
- **Timeout**: Bound waiting time
- **Fallback**: Graceful degradation

## Questions to Explore

1. What bounded context does this belong to?
2. What are the aggregate boundaries?
3. How does this component learn about changes in other contexts?
4. What happens when dependencies are unavailable?
5. How is this component tested in isolation?
6. What are the data consistency requirements?
7. How will this component evolve independently?

## Output Structure

```
## Component: [name]
### Bounded Context: [context]

### Responsibility
Single sentence: what business capability does this provide?

### Aggregate Design
- Root: [entity]
- Invariants protected: [list]
- Consistency boundary: [description]

### Domain Model
[Key entities, value objects, their relationships]

### Domain Events Published
| Event | Trigger | Consumers |
|-------|---------|-----------|

### Integration Points
| Dependency | Pattern | Failure Mode |
|------------|---------|--------------|

### Data Ownership
[What data this component is the source of truth for]

### API Contract
[Key operations, sync vs async, versioning approach]

### Observability
- Key metrics: [list]
- Traces: [span boundaries]
- Alerts: [SLO-based]

### Testing Strategy
- Unit: [aggregate invariants]
- Integration: [adapter tests]
- Contract: [consumer-driven contracts]
```
