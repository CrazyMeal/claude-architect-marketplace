---
description: Deep architectural analysis of a codebase - structure, patterns, coupling, and evolution
argument-hint: [directory]
allowed-tools: Read, Grep, Glob, Bash, Write
model: opus
---

# Codebase Analysis

Comprehensive architectural analysis of an existing codebase.

## Scope

**DO**: Analyze structure, identify patterns/anti-patterns, assess coupling, evaluate evolution readiness, produce report with diagrams

**DON'T**: Modify code, implement fixes

## Analysis Framework

### 1. Structural Analysis
- Entry points and boundaries
- Module/package organization
- Layering discipline
- Dependency direction (outside-in or violations)

### 2. Pattern Recognition
Identify architectural style: layered, hexagonal, clean, vertical slice, microservices, event-driven, or hybrid.

Look for DDD tactical patterns: aggregates, repositories, domain events, value objects.

### 3. Coupling Assessment
- Afferent coupling (incoming dependencies)
- Efferent coupling (outgoing dependencies)
- Instability metric: Ce/(Ca+Ce)
- Circular dependencies

### 4. Anti-Pattern Detection
- Distributed monolith indicators
- God classes (high fan-in/fan-out)
- Feature envy
- Shotgun surgery patterns
- Anemic domain model

### 5. Technical Debt Inventory
Categorize as: Reckless-Deliberate, Reckless-Inadvertent, Prudent-Deliberate, Prudent-Inadvertent

### 6. Evolution Readiness
- Seams for feature addition
- Extraction feasibility
- Test coverage quality
- Configuration flexibility

## Required Outputs

Write all outputs to files:

| Artifact | Location |
|----------|----------|
| Analysis report | `docs/analysis/analysis-[name]-[date].md` |
| Current state diagram | `docs/diagrams/c4-container-current-[name].puml` |
| Dependency graph (if issues) | `docs/diagrams/dependencies-[name].puml` |

### Report Structure
```markdown
# Architecture Analysis: [Name]

## Executive Summary
[2-3 sentences: overall assessment]

## Key Findings
### [Finding 1]
**Evidence**: [file:line references]
**Impact**: [High/Medium/Low]
**Recommendation**: [Action]

## Patterns Identified
## Anti-Patterns Detected
## Technical Debt Assessment
## Evolution Recommendations
```

If ending without artifacts: "Let me produce the analysis report and diagrams."
