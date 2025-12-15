# architecture-design

Collaborative system design with deep architectural knowledge. Covers DDD, distributed systems patterns, 12-factor apps, quality attribute trade-offs, and evolutionary architecture.

## Commands

| Command | Description |
|---------|-------------|
| `/design-system <name>` | Design a complete system architecture with bounded contexts and quality attributes |
| `/design-component <name>` | Design a component with DDD tactical patterns and integration strategies |

## Agent

**system-architect** - Principal architect for design discussions. Engages in peer-level dialogue drawing on DDD, distributed systems theory, and platform engineering. Proactively generates C4 diagrams during design.

## Skill

**system-design** - Activates during architecture discussions. Brings knowledge of architectural styles, DDD patterns, distributed systems fundamentals, and modern patterns (FinOps, API-first, edge computing).

## Knowledge Areas

- **Architectural Styles**: Monolithic, modular monolith, microservices, event-driven, cell-based, serverless
- **Domain-Driven Design**: Bounded contexts, aggregates, context mapping, anti-corruption layers
- **Distributed Systems**: CAP/PACELC, saga patterns, event sourcing, CQRS, outbox pattern
- **Modern Patterns**: FinOps, API-first design, edge computing, multi-cloud strategies
- **Quality Attributes**: Trade-off analysis, fitness functions, evolutionary architecture

## Usage

```
/design-system order-processing

"Design an order processing system. We expect 10K orders/day,
need to integrate with three payment providers, and the team
has strong Go experience."
```

The architect will engage in dialogue about quality priorities, bounded contexts, and architectural trade-offs while generating relevant C4 diagrams.
