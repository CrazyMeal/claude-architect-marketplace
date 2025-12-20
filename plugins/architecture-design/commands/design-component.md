---
description: Design a component with DDD tactical patterns, integration strategies, and visual diagrams
argument-hint: <component-name> [context-file]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Component Design

Deep-dive into a specific component using DDD tactical patterns. **Generate diagrams proactively.**

## Scope

**DO**: Design component internals, generate diagrams (C4 Component, domain models, sequence), write artifacts, analyze patterns

**DON'T**: Write application code—architecture only

## Focus Areas

### Internal Structure
- Aggregate boundaries and invariants
- Entity vs value object decisions
- Repository interfaces
- Domain service identification
- Event definitions

### Integration Strategy
- Sync vs async communication
- API contracts (OpenAPI/AsyncAPI)
- Error handling and resilience
- Idempotency requirements

### Data Considerations
- Persistence strategy
- Consistency boundaries
- Event sourcing applicability
- Read model separation (CQRS)

## Knowledge Base

Reference `shared/core-knowledge.md` for DDD patterns and architectural patterns.

## Diagram Generation

| Aspect | Diagram |
|--------|---------|
| Internal structure | C4 Component |
| Domain model | Class diagram with DDD stereotypes |
| Key flows | Sequence diagram |
| State lifecycle | State machine |

Reference `shared/c4-templates.md` for syntax.

## Dialogue Approach

1. **Understand context**: Where does this fit in the system?
2. **Identify aggregates**: What are the consistency boundaries?
3. **Model the domain**: Entities, value objects, events
4. **Define integration**: How does it communicate?
5. **Consider operations**: Scaling, monitoring, failure modes

## Required Outputs

Before ending, MUST write:
- C4 Component diagram → `docs/diagrams/c4-component-[name].puml`
- Domain model → `docs/diagrams/domain-[name].puml`
- Key decisions as ADR if significant

If ending without artifacts: "Let me generate the component design artifacts first."
