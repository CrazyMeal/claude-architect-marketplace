---
description: Create an Architecture Decision Record following MADR format with proper decision drivers
argument-hint: <decision-title> [output-dir]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Architecture Decision Record

Create an ADR following the MADR (Markdown Any Decision Record) format, adapted for architectural decisions.

## ADR Philosophy

ADRs capture **why** decisions were made, not just what was decided. They serve as:
- Historical record for future team members
- Justification for stakeholders
- Reference for similar future decisions
- Protection against revisiting settled debates

## Decision Drivers

Before writing, identify:
1. **Forces**: What constraints or requirements drive this decision?
2. **Quality attributes**: Which "-ilities" are most important? (Scalability, maintainability, security, etc.)
3. **Constraints**: Budget, timeline, team skills, existing systems?
4. **Stakeholders**: Who cares about this decision?

## MADR Format

```markdown
# ADR-[NUMBER]: [Title in imperative mood: "Use X for Y"]

## Status
[Proposed | Accepted | Deprecated | Superseded by ADR-XXX]

## Date
[YYYY-MM-DD when decision was last updated]

## Decision Makers
[Who participated in making this decision]

## Context and Problem Statement

[Describe the context and problem in 2-3 sentences. What architectural challenge are we facing?]

## Decision Drivers

* [Driver 1: e.g., "Need to handle 10K concurrent users"]
* [Driver 2: e.g., "Team has strong Go expertise"]
* [Driver 3: e.g., "Must integrate with existing Kafka infrastructure"]
* [Driver 4: e.g., "Budget constraints limit managed service options"]

## Considered Options

1. [Option 1]
2. [Option 2]
3. [Option 3]

## Decision Outcome

**Chosen option**: "[Option X]", because [1-2 sentence justification referencing drivers].

### Positive Consequences

* [Benefit 1 - tied to a driver]
* [Benefit 2]

### Negative Consequences

* [Drawback 1 - acknowledged trade-off]
* [Drawback 2]

## Pros and Cons of the Options

### [Option 1]

[Brief description]

* Good, because [advantage]
* Good, because [advantage]
* Bad, because [disadvantage]
* Bad, because [disadvantage]

### [Option 2]

[Brief description]

* Good, because [advantage]
* Bad, because [disadvantage]

### [Option 3]

[Brief description]

* Good, because [advantage]
* Bad, because [disadvantage]

## Links

* [Related ADR](link) - [how it relates]
* [RFC/Spec](link) - [context]
* [External reference](link) - [what it provides]
```

## Decision Categories

Consider which category applies:
- **Technology selection**: Frameworks, languages, databases
- **Architectural pattern**: Microservices, event-driven, CQRS
- **Integration approach**: Sync/async, protocols, contracts
- **Data management**: Storage, caching, consistency
- **Security approach**: Auth, encryption, compliance
- **Operational model**: Deployment, monitoring, scaling

## Writing Guidelines

1. **Title**: Use imperative mood ("Use PostgreSQL for order data", not "Database decision")
2. **Context**: Be specific about the problem, not generic
3. **Drivers**: List concrete, measurable criteria
4. **Options**: Include the obvious ones, explain why they were rejected
5. **Consequences**: Be honest about trade-offs
6. **Links**: Connect to related decisions and external references

## ADR Lifecycle

- **Proposed**: Under discussion
- **Accepted**: Decision made and being implemented
- **Deprecated**: No longer applies (explain why)
- **Superseded**: Replaced by another ADR (link to it)

## Common Pitfalls to Avoid

- Writing ADRs after the fact without real alternatives analysis
- Omitting rejected options (they're valuable for context)
- Being too brief in context (future readers need background)
- Forgetting to update status when decisions change
- Not linking related ADRs together
