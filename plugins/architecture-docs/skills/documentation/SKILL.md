---
name: documentation
description: Create and improve architecture documentation. Use this skill whenever the user needs ADRs, technical specs, RFCs, runbooks, or any architecture documentation -- even if they just say "document this decision," "write up the design," or "we need an RFC for this change."
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Architecture Documentation

Create effective documentation that captures decisions, designs, and operational knowledge. Good architecture docs answer "why" -- the code already shows "what."

## Activation Contexts

- Documenting architectural decisions
- Creating technical specifications
- Writing RFCs for proposals
- Creating C4-based architecture documentation
- Writing operational runbooks
- Reviewing or improving existing documentation

## Document Selection

| Need | Document Type | When to Use |
|------|--------------|-------------|
| Record a decision | ADR | A significant technical decision was made and the reasoning should be preserved |
| Design a feature | Tech Spec | A feature needs detailed design before implementation begins |
| Propose a major change | RFC | A change needs broader discussion and buy-in before committing |
| Explain the system | Architecture Doc | Someone needs to understand how the system works and why |
| Enable operations | Runbook | An on-call engineer needs to diagnose and resolve issues at 3 AM |

## ADR Approach

One ADR per decision. Use the template in `templates/adr-template.md`.

1. **Identify the decision** -- frame it as a question: "How should we handle authentication?"
2. **Gather the drivers** -- what forces, constraints, or requirements led to this decision point?
3. **Document the options seriously** -- include rejected alternatives with honest analysis, not strawmen. Future teams need to understand why Option B lost.
4. **Capture consequences** -- both positive and negative. Every decision has trade-offs; pretending otherwise undermines trust in the document.
5. **Link related ADRs** -- decisions rarely exist in isolation. "Supersedes ADR-0003" or "Constrained by ADR-0007" provides essential context.

## Spec Approach (Modular Output)

Create specs as directories with focused files -- each file is independently consumable by implementation agents:

```
docs/specs/[feature]/
├── README.md          # Overview, goals, non-goals (entry point)
├── api.md             # API contracts, endpoints, schemas
├── data-model.md      # Database schema, entity relationships
├── implementation.md  # Phases, tasks, migration strategy
├── operations.md      # Monitoring, alerts, failure modes
└── decisions.md       # Key decisions with ADR links
```

Use the template in `templates/tech-spec-template.md`.

1. **Start with the problem** -- what are we solving and why now? The urgency context matters.
2. **Define quality attributes** -- measurable requirements, not vague aspirations. "p99 latency under 200ms" beats "should be fast."
3. **Design the solution** -- architecture, data model, APIs in separate files so teams can load only what they need.
4. **Address operations** -- deployment, monitoring, failure modes in a separate file. If you can't explain how to operate it, it's not ready to build.
5. **Plan implementation** -- phases and migration strategy in a separate file. How do we get from here to there safely?

Reference `shared/output-conventions.md` for file locations and naming.

## RFC Approach (Modular Output)

RFCs are for proposals that need broader discussion before commitment. They differ from ADRs (which record decisions already made) and specs (which detail approved designs).

```
docs/rfcs/[number]-[title]/
├── README.md          # Summary, motivation, status
├── design.md          # Detailed technical proposal
├── migration.md       # Rollout plan, backward compatibility
└── alternatives.md    # Seriously considered alternatives with trade-offs
```

1. **State the problem and why now** -- motivation drives urgency. Without a clear "why now," RFCs languish.
2. **Propose a solution at the right level of detail** -- enough to evaluate, not so much that it constrains implementation.
3. **Document alternatives seriously** -- not strawmen. Reviewers should be able to see why the proposed approach wins.
4. **Define success criteria** -- how will we know this worked? What metrics will we watch?
5. **Set a decision deadline** -- RFCs without deadlines never close. State when a decision is needed and why.

## Runbook Approach

Write runbooks for the on-call engineer at 3 AM who has never seen this system before.

Structure each procedure as: **symptom → diagnosis steps → resolution steps → escalation path**.

- Keep commands copy-pasteable with no environment-specific values inline (use variables)
- Include expected output for each diagnostic command so the reader knows if they're on the right track
- List escalation contacts with roles, not just names (names change, roles don't)
- Link to relevant dashboards and alert definitions

## Documentation Principles

- **Right-size the document** -- match documentation effort to the blast radius of the decision. A JSON library choice needs 1 paragraph in an ADR. A new payment system needs a full modular spec directory. Over-documenting trivial decisions wastes effort; under-documenting critical ones creates risk.
- **Make it scannable** -- use headers, bullets, tables, and diagrams. Nobody reads a wall of prose when debugging in production.
- **Keep it current** -- outdated documentation is worse than no documentation because it creates false confidence. Update docs when things change.
- **Connect related docs** -- cross-reference ADRs from specs, link diagrams from design docs. Isolated documents lose context.

## Quality Checklist

- [ ] Clear purpose stated upfront
- [ ] Each file is self-contained in scope (a reader understands its purpose without reading other files, though complex designs are split across focused files with README.md as the entry point)
- [ ] Trade-offs documented honestly
- [ ] Alternatives explained, not dismissed
- [ ] Next steps are clear
- [ ] Related documents linked
- [ ] Diagrams in separate files, referenced by relative path
- [ ] YAML frontmatter with `related-diagrams` and `related-adrs`
