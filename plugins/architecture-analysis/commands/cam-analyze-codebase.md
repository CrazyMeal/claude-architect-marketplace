---
description: Deep architectural analysis of a codebase - structure, patterns, coupling, and evolution opportunities
argument-hint: [directory]
allowed-tools: Read, Grep, Glob, Bash
model: opus
---

# Codebase Architecture Analysis

Perform a comprehensive architectural analysis suitable for informing strategic technical decisions.

## Analysis Dimensions

### 1. Structural Analysis
- **Module boundaries**: Are they well-defined? Do they align with domain concepts?
- **Dependency direction**: Do dependencies point toward abstractions? Any cycles?
- **Layering discipline**: Is there consistent layering? Layer violations?
- **Package cohesion**: Do modules have clear, single responsibilities?

### 2. Domain Model Assessment
- **Bounded context identification**: What domains exist? Are they explicit?
- **Aggregate boundaries**: Are consistency boundaries clear?
- **Domain language**: Is ubiquitous language present in the code?
- **Anemic vs rich domain models**: Where does behavior live?

### 3. Architectural Pattern Recognition
Identify which patterns are in use and how consistently:
- Layered (strict vs relaxed)
- Hexagonal/Ports & Adapters
- Clean Architecture
- Vertical Slice
- Modular Monolith
- Microservices (if multi-repo, analyze boundaries)
- Event-driven elements

### 4. Technical Debt Indicators
Look for patterns that constrain future evolution:
- **God classes/modules**: Too many responsibilities
- **Shotgun surgery**: Changes ripple across many files
- **Feature envy**: Modules reaching into others' internals
- **Primitive obsession**: Domain concepts as primitives
- **Inappropriate intimacy**: Tight coupling between modules
- **Divergent change**: Single module changes for unrelated reasons

### 5. Coupling Analysis
- **Afferent coupling (Ca)**: Who depends on this module?
- **Efferent coupling (Ce)**: Who does this module depend on?
- **Instability (I = Ce/(Ca+Ce))**: Is this module stable enough for its dependents?
- **Abstractness**: Is abstraction level appropriate?
- **Distance from main sequence**: Is there a balanced abstraction/stability?

### 6. Testability Assessment
- **Dependency injection**: Are dependencies injectable?
- **Interface segregation**: Can components be tested in isolation?
- **Side effects**: Are they contained and explicit?
- **Test coverage patterns**: What's tested vs not?

### 7. Evolution Readiness
- **Seams for change**: Where can the system be extended?
- **Strangler fig readiness**: Could parts be extracted?
- **Configuration flexibility**: What requires code changes vs config?
- **Feature flag capability**: Is gradual rollout possible?

## Analysis Process

1. **Read key files first**:
   - Package manifests (package.json, go.mod, pom.xml, etc.)
   - Entry points and composition roots
   - Configuration files
   - Directory structure

2. **Map the architecture**:
   - Identify modules/packages/services
   - Trace key flows through the system
   - Document external integrations

3. **Assess quality dimensions**:
   - Apply the analysis dimensions above
   - Look for patterns and anti-patterns
   - Note inconsistencies

4. **Synthesize findings**:
   - What's the current architectural style?
   - Where are the pain points?
   - What enables or constrains evolution?

## Output Structure

```
## Architecture Analysis: [project-name]

### Executive Summary
[2-3 sentences: What is this, what's its state, what's the key insight]

### Current Architecture
- **Style**: [identified pattern]
- **Key insight**: [main observation]
- **Maturity**: [evolving/stable/stagnant]

### Domain Model
- **Identified contexts**: [list with brief descriptions]
- **Context relationships**: [how they interact]
- **Model richness**: [anemic/mixed/rich]

### Structural Health
| Metric | Assessment | Evidence |
|--------|------------|----------|
| Coupling | [high/medium/low] | [specific example] |
| Cohesion | [high/medium/low] | [specific example] |
| Layering | [strict/relaxed/absent] | [specific example] |

### Technical Debt Register
| Debt Item | Impact | Effort | Priority |
|-----------|--------|--------|----------|
| [issue] | [H/M/L] | [H/M/L] | [1-5] |

### Evolution Opportunities
1. **[opportunity]**: [description, approach, benefit]

### Risks
1. **[risk]**: [description, likelihood, mitigation]

### Recommended Actions
1. [immediate action]
2. [short-term action]
3. [strategic action]
```

Focus on actionable insights. Reference specific files as evidence.
