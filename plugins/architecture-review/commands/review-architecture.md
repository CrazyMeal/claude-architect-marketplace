---
description: Structured architecture review using ATAM-inspired quality attribute analysis
argument-hint: [document-or-directory]
allowed-tools: Read, Grep, Glob
model: opus
---

# Architecture Review

Conduct a rigorous architecture review using quality attribute scenarios and trade-off analysis.

## Review Framework (ATAM-Inspired)

This review draws from the Architecture Tradeoff Analysis Method (ATAM), adapted for practical use.

### Phase 1: Understand the Architecture

1. **Business Context**
   - What business goals drive this architecture?
   - Who are the stakeholders and what do they care about?
   - What are the key constraints?

2. **Architectural Approach**
   - What is the overall architectural style?
   - What are the key structural elements?
   - How do they interact?

3. **Quality Attribute Requirements**
   - What "-ilities" are prioritized?
   - Are there explicit SLAs or quality targets?
   - What quality attributes are in tension?

### Phase 2: Quality Attribute Analysis

For each prioritized quality attribute, develop scenarios:

```
Quality Attribute: [e.g., Performance]
Scenario: [Stimulus] → [System] → [Response] under [Conditions]
Current Support: [How the architecture addresses this]
Risks: [What could cause this to fail]
Sensitivity: [What architectural decisions affect this most]
```

Key quality attributes to assess:
- **Performance**: Latency, throughput, capacity
- **Scalability**: Horizontal scaling, elasticity
- **Availability**: Uptime, fault tolerance, recovery
- **Security**: Confidentiality, integrity, authentication
- **Modifiability**: Ease of change, decoupling
- **Testability**: Observability, isolation
- **Deployability**: CI/CD compatibility, rollback capability
- **Cost Efficiency**: FinOps alignment, scaling economics, data transfer optimization
- **Operational Excellence**: Observability, incident response, runbook readiness

### Phase 3: Trade-off Analysis

Identify architectural decisions that affect multiple quality attributes:

| Decision | Positive Impact | Negative Impact | Sensitivity |
|----------|-----------------|-----------------|-------------|
| [Decision] | [QA improved] | [QA harmed] | [High/Med/Low] |

### Phase 4: Risk Identification

Categorize findings:
- **Risks**: Architectural decisions that may cause problems
- **Sensitivity Points**: Decisions where small changes have large quality impacts
- **Trade-off Points**: Decisions affecting multiple quality attributes

## Output Format

```markdown
## Architecture Review: [System Name]

### Executive Summary
[2-3 sentences: overall assessment, key finding, recommendation]

### Architecture Understanding
- **Style**: [e.g., Microservices with event-driven integration]
- **Key Components**: [Main elements and their roles]
- **Quality Priorities**: [Top 3 quality attributes]

### Quality Attribute Analysis

#### [QA 1: e.g., Performance]
**Requirement**: [Specific target, e.g., p99 < 200ms]
**Scenario**: [Under X load, when Y happens, response within Z]
**Architectural Support**: [How architecture addresses this]
**Assessment**: [Adequate / At Risk / Insufficient]
**Concerns**: [Specific issues]

[Repeat for each priority QA]

### Trade-off Analysis

| Decision | Benefits | Costs | Recommendation |
|----------|----------|-------|----------------|
| [e.g., Async messaging] | Decoupling, scalability | Eventual consistency, debugging complexity | Accept with monitoring |

### Sensitivity Points
1. **[Point]**: Small changes here significantly impact [QA]

### Identified Risks

| Risk | Quality Attribute | Likelihood | Impact | Mitigation |
|------|-------------------|------------|--------|------------|
| [Risk] | [QA affected] | H/M/L | H/M/L | [Action] |

### Recommendations
Prioritized by impact:
1. **[Critical]**: [Recommendation and rationale]
2. **[Important]**: [Recommendation and rationale]
3. **[Consider]**: [Recommendation and rationale]

### Open Questions
- [Questions that need stakeholder input]

### Verdict
[Approve | Approve with conditions | Revise and re-review]
[Brief rationale]
```

## Review Guidelines

- **Understand before judging**: Read fully, ask questions
- **Focus on quality attributes**: Not personal style preferences
- **Be specific**: Reference specific elements, not generalities
- **Suggest alternatives**: Don't just criticize
- **Consider context**: Constraints, team capabilities, timeline
- **Prioritize ruthlessly**: Not all issues are equal
