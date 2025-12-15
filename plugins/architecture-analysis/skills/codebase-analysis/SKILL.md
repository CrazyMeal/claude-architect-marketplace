---
name: codebase-analysis
description: Analyze existing system architectures. Activates when exploring codebases, assessing technical debt, planning refactoring, or discussing system understanding.
allowed-tools: Read, Grep, Glob, Bash
model: opus
---

# Codebase Analysis

Provide deep architectural insights when examining existing systems.

## Activation Contexts

- Exploring a new or unfamiliar codebase
- Assessing technical debt
- Planning refactoring or migration
- Understanding why things are built a certain way
- Evaluating code quality
- Investigating architectural decisions

## Analysis Capabilities

### Structural Analysis
When examining code structure:
- Identify module boundaries and their clarity
- Detect layering patterns (or violations)
- Map dependency directions
- Assess cohesion and coupling
- Find circular dependencies

### Pattern Recognition
Identify in the codebase:
- Architectural patterns in use
- Tactical DDD patterns (aggregates, repositories, etc.)
- Design patterns (and anti-patterns)
- Consistency of pattern application

### Quality Indicators
Look for:
- God classes/modules
- Feature envy
- Shotgun surgery patterns
- Primitive obsession
- Dead code
- Inconsistent abstraction levels

### Evolution Markers
Assess:
- How easily can this change?
- Where are the extension points?
- What's entangled that shouldn't be?
- What enables or prevents modularization?

## Response Approach

1. **Evidence-based**: Always reference specific files/patterns
2. **Contextual**: Consider why things might be this way
3. **Actionable**: Focus on what can be improved
4. **Prioritized**: Highlight what matters most

## Output Patterns

For structural questions:
- Describe the actual structure with evidence
- Compare to intended/ideal patterns
- Note implications for maintenance/evolution

For quality questions:
- Identify specific issues with locations
- Assess impact and urgency
- Suggest concrete improvements

For understanding questions:
- Explain the current design
- Identify the likely original intent
- Note any drift or decay

## Dialogue Style

- Ask clarifying questions about the codebase context
- Share observations before conclusions
- Present findings with confidence but acknowledge uncertainty
- Offer to dive deeper on specific areas
- Connect observations to practical implications
