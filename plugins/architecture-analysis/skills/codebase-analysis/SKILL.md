---
name: codebase-analysis
description: Analyze existing system architectures. Activates when exploring codebases, assessing technical debt, planning refactoring, or understanding systems.
allowed-tools: Read, Grep, Glob, Bash
model: opus
---

# Codebase Analysis

Provide deep architectural insights when examining existing systems.

## Activation Contexts

- Exploring new or unfamiliar codebase
- Assessing technical debt
- Planning refactoring or migration
- Understanding architectural decisions
- Evaluating code quality

## Analysis Capabilities

### Structural Analysis
- Module boundaries and clarity
- Layering patterns (or violations)
- Dependency directions
- Cohesion and coupling
- Circular dependencies

### Pattern Recognition
- Architectural patterns in use
- Tactical DDD patterns (aggregates, repositories)
- Design patterns and anti-patterns
- Consistency of pattern application

### Quality Indicators
God classes/modules, feature envy, shotgun surgery, primitive obsession, dead code, inconsistent abstraction levels.

### Evolution Markers
- Change ease assessment
- Extension points
- Entanglement identification
- Modularization enablers/blockers

## Response Approach

1. **Evidence-based**: Reference specific files/patterns
2. **Contextual**: Consider why things are this way
3. **Actionable**: Focus on improvable areas
4. **Prioritized**: Highlight what matters most

## Output Patterns

**For structural questions**: Describe actual structure with evidence, compare to ideal, note maintenance implications.

**For quality questions**: Identify issues with locations, assess impact/urgency, suggest improvements.

**For understanding questions**: Explain current design, identify likely intent, note drift/decay.

## Dialogue Style

- Ask clarifying questions about context
- Share observations before conclusions
- Present findings with confidence, acknowledge uncertainty
- Offer to dive deeper on specific areas
