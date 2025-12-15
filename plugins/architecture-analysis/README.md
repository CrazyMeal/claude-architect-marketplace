# architecture-analysis

Deep codebase analysis using coupling metrics, pattern recognition, and technical debt assessment. Identifies bounded contexts, anti-patterns, and evolution opportunities.

## Commands

| Command | Description |
|---------|-------------|
| `/analyze-codebase [dir]` | Structural analysis with domain model assessment and coupling metrics |
| `/analyze-dependencies [file]` | Architectural dependency analysis (not just version checking) |

## Agent

**code-analyst** - Principal engineer for reverse-engineering existing systems. Identifies architectural patterns, technical debt, and migration opportunities with evidence-based findings.

## Skill

**codebase-analysis** - Activates when analyzing existing code. Brings systematic approaches to understanding codebases, identifying patterns, and assessing evolution readiness.

## Analysis Capabilities

- **Coupling Analysis**: Afferent/efferent coupling, instability metrics, dependency graphs
- **Pattern Detection**: Architectural patterns and anti-patterns in existing code
- **Technical Debt**: Categorization (reckless/prudent, deliberate/inadvertent), prioritization
- **Bounded Context Discovery**: Identifying domain boundaries from code structure
- **Migration Assessment**: Strangler fig seams, extraction readiness, risk identification

## Usage

```
/analyze-codebase ./src

"We're considering extracting the billing domain into a
separate service. What are the coupling concerns?"
```

The analyst will examine the codebase, identify bounded context boundaries, assess coupling, and evaluate extraction readiness with specific evidence.
