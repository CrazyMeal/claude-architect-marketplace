---
description: Analyze project dependencies for security, maintenance, and architectural concerns
argument-hint: [package-file]
allowed-tools: Read, Grep, Glob, Bash
model: haiku
---

# Dependency Analysis

Analyze project dependencies for issues and improvement opportunities.

## Analysis Steps

1. **Read Dependency Files**
   - package.json, package-lock.json
   - requirements.txt, Pipfile, pyproject.toml
   - go.mod, go.sum
   - Cargo.toml, Gemfile, pom.xml, etc.

2. **Categorize Dependencies**
   - Runtime vs. development
   - Direct vs. transitive
   - Core vs. utility

3. **Assess Each Dependency**
   - Purpose and necessity
   - Maintenance status (if determinable from version dates)
   - Size impact (for frontend)
   - Overlap with other dependencies

## Output Format

```
## Dependency Analysis

### Summary
- Total: [count] ([runtime] runtime, [dev] dev)
- Categories: [breakdown]

### Concerns
| Dependency | Issue | Recommendation |
|------------|-------|----------------|
| ...        | ...   | ...            |

### Optimization Opportunities
1. [opportunity]

### Action Items
- [ ] [specific action]
```

Be concise. Only flag genuine concerns, not theoretical issues.
