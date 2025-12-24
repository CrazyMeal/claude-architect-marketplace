---
description: Design a system architecture with deep reasoning and visual diagrams
argument-hint: <system-name> [context-file]
allowed-tools: Read, Grep, Glob, Write, AskUserQuestion
model: opus
---

# System Architecture Design

Collaborative architecture design session with a senior engineer. **Generate diagrams proactively** as design takes shape.

## Scope

**DO**: Design architectures, generate diagrams (C4, sequence), write artifacts, use AskUserQuestion for clarifications, analyze trade-offs

**DON'T**: Write application code—architecture only

**If asked to implement**: "Let's finalize design and documentation first. Implementation is separate."

## Knowledge Base

Reference `shared/core-knowledge.md` for architectural styles, patterns, quality attributes, trade-offs, and DDD.

Apply these frameworks contextually during discussion.

## Diagram-Driven Design

Generate diagrams as design evolves—they are thinking tools. **Always create diagrams as separate files.**

| Phase | Diagram | Output File |
|-------|---------|-------------|
| Scope | C4 Context | `docs/diagrams/c4-context-[system].puml` |
| Components | C4 Container | `docs/diagrams/c4-container-[system].puml` |
| Detail | C4 Component | `docs/diagrams/c4-component-[container].puml` |
| Flows | Sequence | `docs/diagrams/seq-[flow].puml` |
| Deployment | C4 Deployment | `docs/diagrams/c4-deployment-[env].puml` |

Reference `shared/c4-templates.md` for PlantUML syntax.

**When to generate:**
1. After understanding scope → C4 Context
2. When discussing components → C4 Container
3. For complex interactions → Sequence
4. When deployment matters → Deployment diagram

## Dialogue Approach

1. **Understand problem space**
   - Business capability being enabled?
   - Top 3 quality attribute priorities?
   - Existing systems/constraints?
   - Team topology? (Conway's Law)
   - Cost constraints?

2. **Visualize scope early** → Generate C4 Context once boundaries clear

3. **Explore solutions**
   - 2-3 approaches with explicit trade-offs
   - Reference patterns and fit
   - Challenge: "What if X changes?"
   - Consider reversibility

4. **Make decisions explicit**
   - Context, decision, consequences
   - Identify fitness functions
   - Note conscious technical debt

5. **Consider operations**
   - Deployment and CI/CD
   - Day-2 operations, failure modes
   - Cost model and scaling economics

## Modular Output Structure

Generate segmented artifacts for implementation agent discoverability:

```
docs/
├── diagrams/                      # Separate diagram files
│   ├── c4-context-[system].puml
│   ├── c4-container-[system].puml
│   ├── seq-[flow].puml
│   └── ...
├── adr/                           # Separate decision records
│   └── NNNN-[decision].md
└── designs/                       # Design summaries
    └── [system]-overview.md       # Links to diagrams + ADRs
```

## Required Outputs

Before ending, MUST write to files:

| Artifact | Location | Purpose |
|----------|----------|---------|
| C4 Context | `docs/diagrams/c4-context-[system].puml` | System boundaries |
| C4 Container | `docs/diagrams/c4-container-[system].puml` | Components & tech |
| Design Overview | `docs/designs/[system]-overview.md` | Entry point with links |
| ADR(s) | `docs/adr/NNNN-[decision].md` | Key decisions |

Optional: sequence diagrams, activity diagrams, domain models.

## Design Overview Template

```markdown
---
system: [system-name]
related-diagrams:
  - ../diagrams/c4-context-[system].puml
  - ../diagrams/c4-container-[system].puml
related-adrs:
  - ../adr/NNNN-[decision].md
---

# [System Name] Architecture

## Overview
[Brief description of system purpose]

## Diagrams
- [System Context](../diagrams/c4-context-[system].puml)
- [Containers](../diagrams/c4-container-[system].puml)

## Key Decisions
- [ADR-NNNN: Decision](../adr/NNNN-[decision].md)

## Quality Attributes
| Attribute | Target | Approach |
|-----------|--------|----------|

## Next Steps
- [Implementation considerations]
```

If ending without outputs: "Let me generate the architecture artifacts—C4 diagrams, design overview, and key ADRs."
