---
description: Structured architecture review using ATAM-inspired quality attribute analysis
argument-hint: [document-or-directory]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Architecture Review

Rigorous architecture review using quality attribute scenarios and trade-off analysis.

## Review Framework (ATAM-Inspired)

### Phase 1: Understand the Architecture
1. **Business Context**: Goals, stakeholders, constraints
2. **Architectural Approach**: Style, key elements, interactions
3. **QA Requirements**: Priority "-ilities", SLAs, tensions

### Phase 2: Quality Attribute Analysis

For each priority QA, develop scenario:
```
Quality Attribute: [e.g., Performance]
Scenario: [Stimulus] → [System] → [Response] under [Conditions]
Current Support: [How architecture addresses this]
Risks: [What could cause failure]
Sensitivity: [Decisions affecting this most]
```

Reference `shared/core-knowledge.md` for QA list.

### Phase 3: Trade-off Analysis

| Decision | Positive Impact | Negative Impact | Sensitivity |
|----------|-----------------|-----------------|-------------|
| [Decision] | [QA improved] | [QA harmed] | H/M/L |

### Phase 4: Risk Identification

Categorize:
- **Risks**: Decisions that may cause problems
- **Sensitivity Points**: Small changes → large QA impacts
- **Trade-off Points**: Multiple QAs in conflict

## Required Outputs

Write to files:

| Artifact | Location |
|----------|----------|
| Review report | `docs/reviews/review-[system]-[date].md` |
| Action items | `docs/reviews/actions/[priority]/ACTION-NNN-[title].md` |
| Risk register | `docs/reviews/risks-[system].md` |

### Report Structure
```markdown
## Architecture Review: [System]

### Executive Summary
[2-3 sentences: assessment, key finding, recommendation]
**Verdict**: Approve | Approve with conditions | Revise

### Quality Attribute Analysis
#### [QA 1]
- **Requirement**: [target]
- **Scenario**: [stimulus → response]
- **Assessment**: Adequate / At Risk / Insufficient
- **Concerns**: [specific issues]

### Trade-off Analysis
[Table]

### Sensitivity Points
### Identified Risks
### Recommendations (prioritized)
```

## Review Guidelines

- Understand before judging
- Focus on QAs, not style
- Be specific with evidence
- Suggest alternatives
- Consider context
- Prioritize ruthlessly
