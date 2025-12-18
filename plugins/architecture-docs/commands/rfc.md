---
description: Create a Request for Comments (RFC) document for architectural proposals
argument-hint: <proposal-title> [output-file]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# Request for Comments (RFC)

Create an RFC for major architectural proposals requiring discussion.

## When to Use RFC

- Major architectural changes
- Cross-team initiatives
- New technology adoption
- Significant process changes
- Breaking changes to APIs/contracts

## RFC Structure

```markdown
# RFC-[NUMBER]: [Title]

**Author:** [Name]
**Date:** [YYYY-MM-DD]
**Status:** Draft | Discussion | Accepted | Rejected | Superseded

## Summary
[2-3 sentence overview]

## Motivation
[Why is this change needed? What problem does it solve?]

## Background
[Context needed to understand the proposal]

## Proposal

### Overview
[High-level description]

### Detailed Design
[Technical details, diagrams]

### Migration Path
[How to get from here to there]

## Drawbacks
[Why might we NOT want to do this?]

## Alternatives Considered

### [Alternative 1]
[Description and why not chosen]

## Unresolved Questions
- [Question for discussion]

## Future Possibilities
[What does this enable later?]

## References
- [Related documents, external resources]
```

## RFC Lifecycle

1. **Draft**: Author writing
2. **Discussion**: Open for feedback (set deadline)
3. **Accepted**: Approved for implementation
4. **Rejected**: Not proceeding (document why)
5. **Superseded**: Replaced by another RFC

## Output

Write to `docs/rfcs/rfc-NNNN-[title].md`
