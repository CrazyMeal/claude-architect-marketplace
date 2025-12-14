---
description: Generate a technical specification document
argument-hint: <feature-name> [output-file]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# Technical Specification

Generate a technical spec for a feature or system.

## Process

1. **Understand scope**: What is being specified
2. **Gather requirements**: Functional and non-functional
3. **Design approach**: High-level solution
4. **Detail implementation**: Specific technical details
5. **Write spec**: Following template

## Output Format

```markdown
# Technical Specification: [Feature Name]

**Author:** [name]
**Date:** [date]
**Status:** Draft | Review | Approved

## Overview
[2-3 sentences describing what this spec covers]

## Goals
- [Primary goal]
- [Secondary goals]

## Non-Goals
- [Explicitly out of scope]

## Background
[Context needed to understand this spec]

## Detailed Design

### Architecture
[High-level architecture description]

### Data Model
[Key entities and relationships]

### API Design
[Endpoints, methods, payloads]

### Dependencies
[External systems, libraries]

## Implementation Plan

### Phase 1
- [ ] [Task]

### Phase 2
- [ ] [Task]

## Security Considerations
[Authentication, authorization, data protection]

## Testing Strategy
[How this will be tested]

## Monitoring & Observability
[Metrics, logs, alerts]

## Open Questions
- [ ] [Unresolved question]

## References
- [Links]
```

## Guidelines

- Be specific enough to implement from
- Highlight decisions and their rationale
- Include diagrams where helpful
- List open questions explicitly
