---
description: Analyze dependencies for architectural implications, not just versions
argument-hint: [package-file]
allowed-tools: Read, Grep, Glob, Bash, Write
model: sonnet
---

# Dependency Analysis

Analyze dependencies from an architectural perspective—beyond version checking.

## Scope

**DO**: Analyze architectural implications of dependencies, assess lock-in risk, evaluate abstraction coverage

**DON'T**: Just list outdated packages—that's not architecture

## Analysis Dimensions

### 1. Coupling Assessment
- Direct vs transitive dependencies
- Abstraction coverage (are deps behind interfaces?)
- Replacement difficulty

### 2. Lock-in Risk
| Risk Level | Characteristics |
|------------|-----------------|
| High | Direct usage, no abstraction, proprietary APIs |
| Medium | Behind interface but migration costly |
| Low | Commodity, multiple alternatives, abstracted |

### 3. Architectural Impact
- Framework dependencies (high coupling)
- Infrastructure dependencies (medium coupling)
- Utility dependencies (low coupling)

### 4. Supply Chain Concerns
- Maintenance status
- Security track record
- License compatibility
- Community health

### 5. Upgrade Path Assessment
- Breaking change likelihood
- Migration effort estimation
- Test coverage for deps

## Output Format

```markdown
# Dependency Analysis: [Project]

## Summary
- Total dependencies: [N]
- High-risk: [N]
- Abstraction coverage: [%]

## High-Risk Dependencies
| Dependency | Risk | Reason | Mitigation |
|------------|------|--------|------------|

## Architectural Recommendations
1. [Recommendation with rationale]

## Lock-in Assessment
[Analysis of vendor/framework lock-in]
```

Write report to `docs/analysis/dependencies-[name].md`.
