---
description: Generate a technical specification with quality attribute analysis
argument-hint: <feature-name>
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Technical Specification

Create a modular technical specification for implementation agent discoverability.

## Spec Philosophy

- **Problem-first**: Understand before designing
- **Modular output**: Separate files for each concern
- **Reference, don't embed**: Diagrams in separate files with links
- **Implementation-ready**: Each file serves a specific implementation task

## Modular Output Structure

Create a directory with focused files:

```
docs/specs/[feature-name]/
├── README.md              # Overview, goals, quality attributes
├── api.md                 # API contracts, endpoints, schemas
├── data-model.md          # Database schema, entity relationships
├── implementation.md      # Phases, tasks, migration strategy
├── operations.md          # Monitoring, alerts, failure modes
└── decisions.md           # Key decisions with rationale
```

Reference templates in `templates/spec/` for each file format.

## File Purposes

| File | Purpose | Implementation Agent Use |
|------|---------|-------------------------|
| `README.md` | Problem, goals, scope | Understanding what to build |
| `api.md` | Endpoints, contracts | Building API layer |
| `data-model.md` | Schema, relationships | Building persistence layer |
| `implementation.md` | Phases, tasks | Planning work breakdown |
| `operations.md` | Monitoring, failure modes | Adding observability |
| `decisions.md` | Rationale, ADR links | Understanding constraints |

## Diagram References

Never embed diagrams. Create separate files and reference:

```markdown
## Architecture
See: [System Context](../../diagrams/c4-context-[system].puml)
```

Required diagrams (create in `docs/diagrams/`):
- `c4-context-[feature].puml` - System boundaries
- `c4-container-[feature].puml` - Components and tech choices

Optional diagrams:
- `seq-[flow].puml` - Key interaction flows
- `er-[feature].puml` - Data relationships
- `domain-[feature].puml` - Domain model

## Workflow

1. **Understand** - Clarify problem, goals, constraints
2. **Create directory** - `docs/specs/[feature-name]/`
3. **Write README.md** - Problem, goals, quality attributes
4. **Generate diagrams** - C4 Context and Container in `docs/diagrams/`
5. **Write component files** - api.md, data-model.md based on scope
6. **Write implementation.md** - Phases and tasks
7. **Write operations.md** - Monitoring and failure modes
8. **Write decisions.md** - Link to or create ADRs

## Output Checklist

Before ending, verify:
- [ ] Directory created: `docs/specs/[feature-name]/`
- [ ] README.md with overview and quality attributes
- [ ] At least 2 component files (api.md, data-model.md, etc.)
- [ ] C4 diagrams created in `docs/diagrams/`
- [ ] All diagram references use relative links
- [ ] YAML frontmatter with related-diagrams and related-adrs
