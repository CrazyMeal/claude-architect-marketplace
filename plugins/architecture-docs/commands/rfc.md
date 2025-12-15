---
description: Create a Request for Comments (RFC) document for architectural proposals
argument-hint: <proposal-title> [output-file]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# Request for Comments (RFC)

Create an RFC for proposing significant changes.

## When to Use

- Cross-team architectural changes
- New system introductions
- Major refactoring proposals
- Process or standard changes

## Output Format

```markdown
# RFC: [Title]

**RFC Number:** [number]
**Author(s):** [names]
**Status:** Draft | Discussion | Final Comment | Accepted | Rejected
**Created:** [date]
**Updated:** [date]

## Summary
[One paragraph executive summary]

## Motivation
[Why is this change needed? What problem does it solve?]

## Proposal

### Overview
[High-level description of the proposed change]

### Detailed Design
[Technical details of the proposal]

### Migration Strategy
[How to transition from current state]

## Drawbacks
[Why should we NOT do this?]

## Alternatives

### [Alternative A]
[Description and why not chosen]

### [Alternative B]
[Description and why not chosen]

## Unresolved Questions
- [ ] [Question needing resolution before acceptance]

## Future Possibilities
[What does this enable in the future?]

---

## Discussion

### [Date] - [Author]
[Comment or concern]

### [Date] - [Author]
[Response or additional input]
```

## Guidelines

- Assume readers have context but spell out assumptions
- Focus on the "why" as much as the "what"
- Be honest about drawbacks
- Leave room for discussion
