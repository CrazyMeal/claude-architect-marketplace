---
description: Create a Request for Comments (RFC) document for architectural proposals
argument-hint: <proposal-title>
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Request for Comments (RFC)

Create a modular RFC for major architectural proposals.

## When to Use RFC

- Major architectural changes
- Cross-team initiatives
- New technology adoption
- Significant process changes
- Breaking changes to APIs/contracts

## Modular Output Structure

Create a directory with focused files:

```
docs/rfcs/[rfc-number]-[title]/
├── README.md              # Summary, motivation, status (entry point)
├── design.md              # Detailed technical design
├── migration.md           # Migration path, rollout plan
└── alternatives.md        # Considered alternatives with trade-offs
```

## File Purposes

| File | Purpose | Reviewer Focus |
|------|---------|----------------|
| `README.md` | Motivation, overview, risks | Understanding what and why |
| `design.md` | Architecture, API, data | Evaluating technical approach |
| `migration.md` | Phases, rollout, rollback | Planning implementation |
| `alternatives.md` | Trade-off analysis | Validating decision |

## Diagram References

Never embed diagrams. Create separate files and reference:

```markdown
## Architecture
See: [System Context](../../diagrams/c4-context-[system].puml)
```

Required diagrams (create in `docs/diagrams/`):
- `c4-context-[rfc-name].puml` - System boundaries
- `c4-container-[rfc-name].puml` - Components and tech choices

## RFC Lifecycle

1. **Draft**: Author writing
2. **Discussion**: Open for feedback (set deadline)
3. **Accepted**: Approved for implementation
4. **Rejected**: Not proceeding (document why)
5. **Superseded**: Replaced by another RFC

## Workflow

1. **Determine RFC number** - Check existing RFCs in `docs/rfcs/`
2. **Create directory** - `docs/rfcs/[rfc-number]-[title]/`
3. **Write README.md** - Summary, motivation, risks
4. **Generate diagrams** - C4 Context and Container in `docs/diagrams/`
5. **Write design.md** - Technical details with diagram references
6. **Write migration.md** - Rollout phases and strategy
7. **Write alternatives.md** - Document rejected approaches

## Output Checklist

Before ending, verify:
- [ ] Directory created: `docs/rfcs/[rfc-number]-[title]/`
- [ ] README.md with summary and motivation
- [ ] design.md with technical approach
- [ ] C4 diagrams created in `docs/diagrams/`
- [ ] All diagram references use relative links
- [ ] YAML frontmatter with related-diagrams
