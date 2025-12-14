---
description: Create an Architecture Decision Record (ADR)
argument-hint: <decision-title> [output-dir]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# Architecture Decision Record

Create a new ADR documenting an architectural decision.

## Process

1. **Gather context**: Ask about the decision if not provided
2. **Identify existing ADRs** in output directory for numbering
3. **Generate ADR** following standard template
4. **Save to file** with sequential number

## Required Information

- What is the decision about?
- What options were considered?
- What was decided and why?
- What are the consequences?

## Output Format

```markdown
# ADR-[NUMBER]: [TITLE]

## Status
[Proposed | Accepted | Deprecated | Superseded by ADR-X]

## Context
[What is the issue motivating this decision?]

## Decision
[What is the change being proposed/decided?]

## Consequences

### Positive
- [benefit]

### Negative
- [drawback]

### Neutral
- [side effect]

## Alternatives Considered

### [Alternative 1]
- Pros: [...]
- Cons: [...]
- Why rejected: [...]

## Related
- [Links to related ADRs, docs, or issues]
```

## Guidelines

- Keep context focused on the specific decision
- Be explicit about trade-offs
- Document alternatives even if obvious
- Link to related decisions
