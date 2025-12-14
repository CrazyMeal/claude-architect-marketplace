---
description: Review an Architecture Decision Record for completeness and quality
argument-hint: <adr-file>
allowed-tools: Read, Grep, Glob
model: haiku
---

# ADR Review

Review an ADR for quality and completeness.

## Review Checklist

- [ ] **Context**: Is the problem clearly stated?
- [ ] **Decision**: Is the decision explicit and clear?
- [ ] **Rationale**: Is the "why" explained?
- [ ] **Alternatives**: Are other options documented?
- [ ] **Consequences**: Are trade-offs acknowledged?
- [ ] **Status**: Is status appropriate?

## Output Format

```
## ADR Review: [Title]

### Completeness: [X/6 criteria met]
[List which criteria pass/fail]

### Feedback

#### Required Changes
- [Must-fix issue]

#### Suggestions
- [Nice-to-have improvement]

### Questions
- [Clarifying question]

### Verdict
[Approve | Revise]
```

Keep review concise. Focus on actionable feedback.
