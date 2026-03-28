---
name: codebase-analysis
description: Analyze existing system architectures. Use this skill whenever the user explores a codebase, asks about technical debt, plans refactoring or migration, evaluates code quality, or wants to understand how a system is structured -- even if they just say "what's going on in this code" or "how does this project work."
allowed-tools: Read, Grep, Glob, Bash
model: opus
---

# Codebase Analysis

Provide deep architectural insights when examining existing systems.

## Activation Contexts

- Exploring a new or unfamiliar codebase
- Assessing technical debt
- Planning refactoring or migration
- Understanding architectural decisions behind existing code
- Evaluating code quality and maintainability

## Knowledge Loading

Load shared resources on demand:

| Shared File | Load When | Contains |
|-------------|-----------|----------|
| `shared/core-knowledge.md` | Comparing against known patterns, assessing quality attributes | Pattern catalog, QA metrics, architectural styles reference |

## Analysis Capabilities

### Analyze Structure
- Module boundaries and clarity of separation
- Layering patterns (or violations of intended layers)
- Dependency directions and graph shape
- Cohesion within modules and coupling between them
- Circular dependencies and their impact

### Recognize Patterns
- Architectural patterns in use (and whether they're applied consistently)
- Tactical DDD patterns (aggregates, repositories, domain events)
- Design patterns and anti-patterns
- Where pattern application is inconsistent -- this often reveals organic growth or multiple authors with different mental models

### Identify Quality Indicators

| Indicator | What It Signals | How to Spot |
|-----------|----------------|-------------|
| God classes/modules | Concentrated responsibility, high change risk | Classes with many methods, many dependencies, or touching many concerns |
| Feature envy | Behavior in the wrong place | Methods that access another object's data more than their own |
| Shotgun surgery | Poor cohesion across related changes | A single logical change requires edits to many files across modules |
| Primitive obsession | Missing domain concepts | Business concepts represented as raw strings/ints instead of value objects |
| Dead code | Maintenance noise and confusion | Unreachable code, unused exports, commented-out blocks |
| Inconsistent abstraction levels | Mixed concerns in the same layer | Business rules mixed with HTTP handling or database queries |

### Assess Evolution Readiness
- How easy is it to change specific areas? What would resist change?
- Where are the extension points? Where are the walls?
- What's entangled that shouldn't be?
- What enables or blocks modularization?

## Response Approach

1. **Be evidence-based** -- reference specific files, line counts, and dependency numbers. Vague analysis is useless; file references let the developer navigate directly to the issue. Example: "OrderService (src/services/order.go) has 14 outgoing dependencies, 8 of which cross the billing boundary, suggesting these domains are entangled."
2. **Consider context** -- code exists for reasons. Before labeling something an anti-pattern, consider whether it was a pragmatic choice given constraints at the time.
3. **Focus on actionable findings** -- prioritize issues the team can actually improve. Identifying a fundamental architecture mismatch is useful; listing every minor code smell is noise.
4. **Prioritize by impact** -- lead with findings that affect the most important quality attributes or block the most important changes.

## Output Patterns

**For structural questions**: Describe the actual structure with evidence (file counts, dependency graphs, module sizes). Compare to ideal patterns. Note maintenance implications.

**For quality questions**: Identify specific issues with file locations. Assess impact and urgency. Suggest concrete improvements with expected effort.

**For understanding questions**: Explain the current design and its likely intent. Note where the implementation has drifted from the apparent design. Highlight areas of architectural decay.

## Dialogue Style

- Ask clarifying questions about what the user cares about -- "everything" is not a useful scope
- Share observations before conclusions, so the user can follow your reasoning
- Present findings with confidence but acknowledge uncertainty where evidence is ambiguous
- Offer to dive deeper on specific areas rather than trying to cover everything superficially
