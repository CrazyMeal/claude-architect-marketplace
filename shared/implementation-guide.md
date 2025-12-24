# Implementation Agent Guide

This guide helps implementation agents locate the right documentation for their tasks.

## Document Discovery by Task

### "I need to implement a new API endpoint"

1. Check spec API design: `docs/specs/[feature]/api.md`
2. Check related sequence diagrams: `docs/diagrams/seq-*.puml`
3. Check relevant ADRs for constraints: `docs/adr/*.md`

### "I need to implement database changes"

1. Check spec data model: `docs/specs/[feature]/data-model.md`
2. Check ER diagrams: `docs/diagrams/er-*.puml`
3. Check domain models: `docs/diagrams/domain-*.puml`

### "I need to understand system boundaries"

1. Check C4 Context: `docs/diagrams/c4-context-*.puml`
2. Check design overview: `docs/designs/*-overview.md`

### "I need to understand component internals"

1. Check C4 Container: `docs/diagrams/c4-container-*.puml`
2. Check C4 Component: `docs/diagrams/c4-component-*.puml`
3. Check component design: `docs/designs/component-*.md`

### "I need to add monitoring/observability"

1. Check spec operations: `docs/specs/[feature]/operations.md`
2. Check deployment diagrams: `docs/diagrams/c4-deployment-*.puml`

### "I need to understand a design decision"

1. Check ADRs: `docs/adr/*.md`
2. Check spec decisions: `docs/specs/[feature]/decisions.md`
3. Check RFC alternatives: `docs/rfcs/*/alternatives.md`

## Document Structure

```
docs/
├── diagrams/              # Visual representations (load individually)
│   ├── c4-context-*.puml      → System boundaries, external actors
│   ├── c4-container-*.puml    → Deployable components, tech choices
│   ├── c4-component-*.puml    → Internal structure of a container
│   ├── c4-deployment-*.puml   → Infrastructure mapping
│   ├── seq-*.puml             → Interaction flows
│   ├── activity-*.puml        → Business processes
│   ├── domain-*.puml          → DDD models
│   └── er-*.puml              → Data relationships
│
├── specs/[feature]/       # Feature specifications (load by concern)
│   ├── README.md              → Overview, goals, quality attributes
│   ├── api.md                 → API contracts, endpoints
│   ├── data-model.md          → Database schema, entities
│   ├── implementation.md      → Build phases, tasks
│   ├── operations.md          → Monitoring, failure modes
│   └── decisions.md           → Key decisions, ADR links
│
├── designs/               # Architecture summaries
│   ├── [system]-overview.md   → System design entry point
│   └── component-[name].md    → Component design entry point
│
├── adr/                   # Architecture Decision Records
│   └── NNNN-[title].md        → Individual decisions
│
├── rfcs/[number]-[title]/ # RFCs (load by concern)
│   ├── README.md              → Summary, motivation
│   ├── design.md              → Technical details
│   ├── migration.md           → Rollout plan
│   └── alternatives.md        → Rejected options
│
└── reviews/               # Architecture reviews
    └── review-*.md            → Review findings
```

## YAML Frontmatter for Discovery

All modular docs include frontmatter for programmatic discovery:

```yaml
---
feature: [feature-name]
component: [api|data|ops|...]
related-diagrams:
  - ../diagrams/c4-container-system.puml
  - ../diagrams/seq-flow.puml
related-adrs:
  - ../adr/0001-decision.md
---
```

## Loading Strategy

1. **Start small**: Load only the specific file for your task
2. **Follow references**: Use cross-references to load related docs as needed
3. **Check frontmatter**: Use `related-diagrams` and `related-adrs` for context
4. **Avoid loading entire directories**: Each file is self-contained with references
