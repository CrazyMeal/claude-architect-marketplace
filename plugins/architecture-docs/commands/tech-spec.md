---
description: Generate a technical specification with proper quality attribute analysis
argument-hint: <feature-name> [output-file]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Technical Specification

Create a comprehensive technical specification that enables implementation while capturing key architectural decisions.

## Specification Purpose

A good tech spec:
- Enables implementation without constant clarification
- Documents the "why" behind design choices
- Identifies risks and unknowns upfront
- Serves as contract between teams
- Provides basis for review and feedback

## Specification Framework

```markdown
# Technical Specification: [Feature Name]

**Author(s):** [Names]
**Reviewers:** [Names]
**Created:** [Date]
**Last Updated:** [Date]
**Status:** Draft | In Review | Approved | Implemented | Obsolete

## Executive Summary

[One paragraph: What is this, why are we doing it, what's the key approach?]

## Problem Statement

### Background
[Context needed to understand this work. What exists today?]

### Problem
[Specific problem being solved. What pain does this address?]

### Scope
[What is and isn't included in this spec?]

## Goals and Non-Goals

### Goals
1. [Measurable goal 1]
2. [Measurable goal 2]

### Non-Goals
1. [Explicitly excluded scope 1]
2. [Explicitly excluded scope 2]

## Quality Attributes

Prioritized quality requirements for this feature:

| Attribute | Requirement | Measurement |
|-----------|-------------|-------------|
| Performance | [e.g., p99 < 200ms] | [How measured] |
| Scalability | [e.g., 10K concurrent users] | [How verified] |
| Availability | [e.g., 99.9% uptime] | [How measured] |
| Security | [e.g., OWASP Top 10 compliant] | [How verified] |

## Design

### Architecture Overview

[High-level description with diagram (C4 Container level)]

### Component Design

#### [Component 1]
- **Responsibility**: [Single sentence]
- **Key interfaces**: [API/events]
- **Dependencies**: [What it needs]
- **Data owned**: [What it's source of truth for]

#### [Component 2]
[Same structure]

### Data Model

[Entity descriptions, relationships, key constraints]

### API Design

#### [Endpoint/Event 1]
```
[Request/Event schema]
```
```
[Response/Result schema]
```

### Integration Points

| System | Direction | Protocol | Data | Failure Handling |
|--------|-----------|----------|------|------------------|
| [System] | In/Out | [Protocol] | [What flows] | [What happens on failure] |

## Implementation

### Phased Approach

#### Phase 1: [Name] - [Timeframe if known]
- [ ] [Deliverable 1]
- [ ] [Deliverable 2]

#### Phase 2: [Name]
- [ ] [Deliverable 1]

### Migration Strategy

[How existing systems/data will transition]

### Feature Flags

[What flags control rollout, how to enable/disable]

## Security Considerations

### Threat Model
[Key threats and how they're addressed]

### Authentication/Authorization
[How access is controlled]

### Data Protection
[Encryption, PII handling, compliance]

## Operational Considerations

### Deployment
[How this gets deployed, dependencies, ordering]

### Observability

**Metrics:**
- [Metric 1]: [What it measures, alert threshold]

**Logs:**
- [Key log events and their meaning]

**Traces:**
- [Key spans and what they cover]

### Failure Modes

| Failure | Detection | Impact | Recovery |
|---------|-----------|--------|----------|
| [Failure mode] | [How detected] | [What breaks] | [How to recover] |

### Runbook
[Link to operational runbook or key procedures]

## Testing Strategy

### Unit Tests
[Key areas and approach]

### Integration Tests
[What interactions are tested]

### E2E Tests
[Key scenarios covered]

### Performance Tests
[Load testing approach]

## Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| [Risk] | H/M/L | H/M/L | [How addressed] |

## Open Questions

- [ ] [Question 1 - who needs to answer]
- [ ] [Question 2]

## Alternatives Considered

### [Alternative 1]
[Description, why rejected]

### [Alternative 2]
[Description, why rejected]

## References

- [Related ADRs]
- [Related specs]
- [External documentation]
```

## Writing Guidelines

1. **Start with the problem**: Don't jump to solution
2. **Be specific**: "Fast" is not a requirement, "p99 < 100ms" is
3. **Address failure modes**: How does this fail? How do you recover?
4. **Include operational concerns**: Day-2 matters as much as day-1
5. **Document alternatives**: Show your reasoning
6. **Keep it updated**: Mark obsolete sections, don't delete history
