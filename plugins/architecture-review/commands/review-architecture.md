---
description: Review an architecture design or document for quality and risks
argument-hint: [document-or-directory]
allowed-tools: Read, Grep, Glob
model: sonnet
---

# Architecture Review

Provide a structured review of an architecture design.

## Review Process

1. **Read the design**: Understand what's being proposed
2. **Identify strengths**: What works well
3. **Find weaknesses**: Potential issues
4. **Assess risks**: What could go wrong
5. **Suggest improvements**: Concrete recommendations

## Review Dimensions

- **Correctness**: Does it solve the stated problem?
- **Completeness**: Are all aspects addressed?
- **Clarity**: Is it understandable?
- **Consistency**: Do patterns align?
- **Scalability**: Will it handle growth?
- **Security**: Are threats addressed?
- **Operability**: Can it be run and maintained?
- **Testability**: Can it be verified?

## Output Format

```
## Architecture Review

### Summary
[1-2 sentence overall assessment]

### Strengths
1. [Strength with explanation]
2. [Strength with explanation]

### Concerns

#### Critical
- **[Issue]**: [Description]
  - Impact: [What could go wrong]
  - Suggestion: [How to address]

#### Moderate
- **[Issue]**: [Description]
  - Suggestion: [How to address]

#### Minor
- [Issue]: [Brief suggestion]

### Questions
1. [Clarifying question]

### Recommendations
1. [Prioritized recommendation]
2. [Prioritized recommendation]

### Overall Assessment
[Approve | Approve with changes | Request revision]
[Brief rationale]
```

## Guidelines

- Be constructive, not just critical
- Prioritize feedback by impact
- Suggest solutions, not just problems
- Acknowledge constraints mentioned in design
