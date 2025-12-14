---
description: Analyze dependencies for architectural implications, not just versions
argument-hint: [package-file]
allowed-tools: Read, Grep, Glob, Bash
model: sonnet
---

# Dependency Architecture Analysis

Go beyond version checking to understand architectural implications of dependencies.

## Analysis Framework

### 1. Dependency Classification

**By Architectural Role**:
- **Core domain**: Libraries that shape your domain model
- **Infrastructure**: Database, messaging, HTTP clients
- **Application framework**: The foundation (Spring, Express, etc.)
- **Cross-cutting**: Logging, metrics, security
- **Utility**: Helpers that could be replaced easily

**By Coupling Level**:
- **Deep integration**: Pervasive throughout codebase
- **Adapter pattern**: Wrapped behind abstractions
- **Isolated usage**: Contained to specific modules
- **Transitive only**: Brought in by other deps

### 2. Risk Assessment

**Vendor/Project Risk**:
- Maintenance activity (commits, releases, response time)
- Community health (contributors, adoption)
- License implications
- Funding/sustainability model

**Technical Risk**:
- Breaking change history
- API stability
- Performance characteristics
- Security track record

**Coupling Risk**:
- How painful would replacement be?
- Are there abstraction layers protecting you?
- Is business logic entangled with library idioms?

### 3. Architectural Implications

Consider how dependencies affect:
- **Testability**: Do they make testing harder?
- **Deployment**: Do they constrain how you deploy?
- **Performance**: What's their runtime impact?
- **Observability**: Do they integrate with your monitoring?
- **Scalability**: Any single-instance assumptions?

### 4. Strategic Concerns

- **Build vs buy evolution**: Should any deps become custom code?
- **Consolidation opportunities**: Multiple libs doing similar things?
- **Abstraction opportunities**: Where should you wrap dependencies?
- **Upgrade paths**: Any deps blocking language/framework upgrades?

## Output Structure

```
## Dependency Analysis

### Overview
- Total dependencies: [X direct, Y transitive]
- Risk profile: [summary]

### Architectural Dependencies
| Dependency | Role | Coupling | Risk | Notes |
|------------|------|----------|------|-------|
| [name] | [core/infra/util] | [deep/wrapped/isolated] | [H/M/L] | [key concern] |

### Strategic Concerns

#### High-Risk Dependencies
1. **[dep]**: [why risky, what to do]

#### Abstraction Recommendations
1. **[dep]**: [wrap because...]

#### Consolidation Opportunities
1. **[dep1, dep2]**: [overlap, recommendation]

### Action Items
- [ ] [prioritized action]
```

Focus on architectural implications, not just outdated versions.
