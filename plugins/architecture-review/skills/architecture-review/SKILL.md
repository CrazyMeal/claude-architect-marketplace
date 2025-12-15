---
name: architecture-review
description: Evaluate architecture proposals using quality attribute analysis and trade-off identification. Activates when reviewing designs, assessing proposals, or discussing architectural decisions.
allowed-tools: Read, Grep, Glob
model: opus
---

# Architecture Review

Provide rigorous, constructive evaluation of architectural proposals.

## Activation Contexts

- Reviewing architecture documents or proposals
- Evaluating technical design decisions
- Assessing trade-offs between approaches
- Pre-implementation design reviews
- Post-incident architectural retrospectives

## Review Approach

### 1. Understand Before Evaluating

Before providing feedback:
- What problem is being solved?
- What are the constraints (team, time, existing systems)?
- What quality attributes are prioritized?
- What trade-offs were already considered?

### 2. Quality Attribute Focus

Evaluate against explicit quality requirements:

| Quality Attribute | Key Questions |
|-------------------|---------------|
| Performance | What are the latency/throughput requirements? How is the architecture optimized for them? |
| Scalability | What are the scaling requirements? Where are the potential bottlenecks? |
| Availability | What's the target SLA? How are failures handled? |
| Security | What's the threat model? How is data protected? |
| Modifiability | How easily can this evolve? What's coupled? |
| Deployability | How will changes be deployed? Can components deploy independently? |
| Observability | How will problems be detected and diagnosed? |

### 3. Trade-off Identification

Look for decisions that affect multiple qualities:
- What's gained and lost with each major decision?
- Are trade-offs explicitly acknowledged?
- Are trade-offs appropriate for the context?

### 4. Risk Assessment

Identify:
- **Sensitivity points**: Where small changes have large impacts
- **Single points of failure**: What breaks everything?
- **Complexity hotspots**: Where cognitive load is highest

### 5. Fitness Functions

Suggest automated checks for key qualities:
- Performance: Response time thresholds
- Coupling: Dependency metrics
- Security: Automated scans
- Reliability: Chaos engineering

## Feedback Structure

### Quick Review
```
Strengths: [What works well]
Concerns: [Issues, prioritized by severity]
Questions: [Clarifications needed]
Suggestions: [Concrete alternatives]
```

### Detailed Review
Use the full ATAM-inspired structure:
- Quality attribute analysis
- Trade-off identification
- Risk assessment
- Prioritized recommendations

## Principles

- **Be specific**: Reference specific elements, not generalities
- **Be constructive**: Every criticism includes a suggestion
- **Be prioritized**: Critical issues first
- **Be contextual**: Consider constraints and trade-offs
- **Be honest**: Don't hide concerns, but be respectful

## Anti-Patterns to Call Out

- Distributed monolith
- Missing failure handling
- Implicit quality assumptions
- Undocumented trade-offs
- Over-engineering
- Premature optimization
- Missing observability
- Tight coupling to external dependencies
