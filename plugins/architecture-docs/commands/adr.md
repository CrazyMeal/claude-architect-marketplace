---
description: Create an Architecture Decision Record following MADR format
argument-hint: <decision-title> [output-dir]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Architecture Decision Record

Create an ADR following MADR (Markdown Any Decision Record) format.

## ADR Philosophy

ADRs capture **why** decisions were made:
- Historical record for future team members
- Justification for stakeholders
- Reference for similar decisions
- Protection against revisiting settled debates

## Before Writing

Identify:
1. **Forces**: Constraints driving this decision
2. **Quality attributes**: Priority "-ilities"
3. **Constraints**: Budget, timeline, skills, systems
4. **Stakeholders**: Who cares?

## MADR Format

```markdown
# ADR-[NUMBER]: [Title in imperative: "Use X for Y"]

## Status
[Proposed | Accepted | Deprecated | Superseded by ADR-XXX]

## Date
[YYYY-MM-DD]

## Decision Makers
[Participants]

## Context and Problem Statement
[2-3 sentences: What challenge are we facing?]

## Decision Drivers
* [Driver 1: e.g., "10K concurrent users"]
* [Driver 2: e.g., "Team Go expertise"]

## Considered Options
1. [Option 1]
2. [Option 2]
3. [Option 3]

## Decision Outcome
**Chosen**: "[Option X]", because [justification referencing drivers].

### Positive Consequences
* [Benefit tied to driver]

### Negative Consequences
* [Acknowledged trade-off]

## Pros and Cons of Options

### [Option 1]
* Good, because [advantage]
* Bad, because [disadvantage]

## Links
* [Related ADR](link)
```

## Writing Guidelines

- **Title**: Imperative mood ("Use PostgreSQL for orders")
- **Context**: Specific, not generic
- **Drivers**: Concrete, measurable
- **Options**: Include rejected alternatives with reasons
- **Consequences**: Be honest about trade-offs

## ADR Lifecycle

- **Proposed**: Under discussion
- **Accepted**: Decision made
- **Deprecated**: No longer applies
- **Superseded**: Replaced by another ADR

## Output

Write to `docs/adr/NNNN-[title].md`

Determine next number by checking existing ADRs in directory.
