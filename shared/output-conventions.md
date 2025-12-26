# Output Conventions

## Mandatory Artifact Production

**Every architecture session MUST produce written artifacts.** Never end having only discussed.

If user tries to end without artifacts: "Let me generate the artifacts first."

## Modular Documentation Principle

**Segment outputs for implementation agent discoverability.** Each artifact should be focused and independently consumable. Never embed diagrams inline—always reference separate files.

Benefits:
- Implementation agents load only what they need
- Reduced context window usage
- Clear task-to-document mapping
- Easier maintenance and updates

## Standard Output Locations

### Diagrams (Always Separate Files)

| Diagram Type | Location | Naming |
|--------------|----------|--------|
| C4 Context | `docs/diagrams/` | `c4-context-[system].puml` |
| C4 Container | `docs/diagrams/` | `c4-container-[system].puml` |
| C4 Component | `docs/diagrams/` | `c4-component-[container].puml` |
| C4 Deployment | `docs/diagrams/` | `c4-deployment-[env].puml` |
| Sequence | `docs/diagrams/` | `seq-[flow].puml` |
| Activity | `docs/diagrams/` | `activity-[process].puml` |
| Domain Model | `docs/diagrams/` | `domain-[context].puml` |
| ER Diagram | `docs/diagrams/` | `er-[context].puml` |

### Decisions

| Artifact | Location | Naming |
|----------|----------|--------|
| ADRs | `docs/adr/` | `NNNN-[title].md` |

### Technical Specifications (Modular Structure)

Specs are **directories** with focused files:

```
docs/specs/[feature-name]/
├── README.md              # Overview, goals, non-goals (entry point)
├── api.md                 # API contracts, endpoints, schemas
├── data-model.md          # Database schema, entity relationships
├── implementation.md      # Phases, tasks, migration strategy
├── operations.md          # Monitoring, alerts, failure modes
└── decisions.md           # Key decisions with rationale (links to ADRs)
```

| File | Purpose | When to Load |
|------|---------|--------------|
| `README.md` | Problem context, scope | Understanding what to build |
| `api.md` | API contracts | Implementing endpoints |
| `data-model.md` | Data structures | Implementing persistence |
| `implementation.md` | Build phases | Planning implementation tasks |
| `operations.md` | Operational concerns | Adding observability |
| `decisions.md` | Design rationale | Understanding why |

### RFCs (Modular Structure)

```
docs/rfcs/[rfc-number]-[title]/
├── README.md              # Summary, motivation, status
├── design.md              # Detailed technical design
├── migration.md           # Migration path, rollout plan
└── alternatives.md        # Considered alternatives with trade-offs
```

### Reviews

| Artifact | Location | Naming |
|----------|----------|--------|
| Reviews | `docs/reviews/` | `review-[system]-[date].md` |
| Actions | `docs/reviews/actions/[priority]/` | `ACTION-NNN-[title].md` |

## Cross-Reference Protocol

### Referencing Diagrams

Always link to diagrams, never embed:

```markdown
## Architecture

See: [System Context](../diagrams/c4-context-myapp.puml) | [Containers](../diagrams/c4-container-myapp.puml)

For authentication flow, see [seq-auth.puml](../diagrams/seq-auth.puml).
```

### Referencing Decisions

Link to ADRs for rationale:

```markdown
## Database Choice

PostgreSQL selected per [ADR-0003](../adr/0003-use-postgresql.md).
```

### Implementation Context Header

Every modular doc should include a header for implementation agents:

```markdown
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

## Document Consistency Protocol

### Before Writing
1. Read `docs/` for existing architecture documentation
2. Check `docs/adr/` for decisions that may affect your work
3. Check `docs/diagrams/` to understand current state

### When Updating
- Design changes existing decision → New ADR that supersedes
- Design changes system boundaries → Update ALL affected C4 diagrams
- Design adds/removes components → Update Container diagram AND related docs
- Spec changes → Update only the affected modular file

### Consistency Checks
- New decisions don't contradict existing ADRs
- Diagrams reflect current design state
- Component names consistent across all documents
- Technology choices match between ADRs and diagrams
- Cross-references are valid (no broken links)

**If you find inconsistencies, fix them proactively or flag them explicitly.**

## Review Action File Format

```markdown
# ACTION-NNN: [Title]

## Priority
Critical | Important | Consider

## Finding
[What was identified]

## Impact
[Why this matters - quality attributes affected]

## Recommendation
[Specific action to take]

## Acceptance Criteria
- [ ] [Measurable outcome 1]
- [ ] [Measurable outcome 2]

## Related
- Review: [link to main review]
- Affected components: [list]
- Diagrams: [links to relevant diagrams]
- Specs: [links to relevant spec files]
```
