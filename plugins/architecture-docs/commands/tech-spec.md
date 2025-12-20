---
description: Generate a technical specification with quality attribute analysis
argument-hint: <feature-name> [output-file]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Technical Specification

Create a comprehensive technical specification document.

## Spec Philosophy

Problem-first, quality-driven design that considers the full lifecycle.

## Spec Structure

```markdown
# Technical Specification: [Feature Name]

**Author:** [Name]
**Date:** [YYYY-MM-DD]
**Status:** Draft | Review | Approved

## Problem Statement
[What problem are we solving? Why now?]

## Goals
- [Measurable goal 1]
- [Measurable goal 2]

## Non-Goals
- [Explicitly out of scope]

## Quality Attributes

| Attribute | Requirement | Measurement |
|-----------|-------------|-------------|
| Performance | [target] | [how measured] |
| Scalability | [target] | [how measured] |
| Availability | [target] | [how measured] |

## Design

### Architecture Overview
[C4 diagrams, system context]

### Data Model
[Entity relationships, schemas]

### API Design
[Endpoints, contracts]

### Key Decisions
[Important choices with rationale]

## Implementation Plan

### Phase 1: [Name]
- [Deliverable]
- [Milestone]

### Migration Strategy
[If applicable]

### Feature Flags
[Rollout approach]

## Operational Concerns

### Deployment
[Strategy, requirements]

### Monitoring
[Key metrics, alerts]

### Failure Modes
[What can fail, recovery]

## Security Considerations
[Threats, mitigations]

## Testing Strategy
[Unit, integration, E2E approach]

## Open Questions
- [Question needing resolution]

## Related Documents
- [ADRs, other specs]
```

## Output

Write to `docs/specs/spec-[feature].md`
