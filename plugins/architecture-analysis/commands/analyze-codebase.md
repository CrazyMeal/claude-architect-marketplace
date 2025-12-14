---
description: Analyze codebase architecture to identify structure, patterns, and issues
argument-hint: [directory]
allowed-tools: Read, Grep, Glob, Bash
model: sonnet
---

# Codebase Architecture Analysis

Analyze a codebase to understand its architecture and identify improvement opportunities.

## Analysis Process

1. **Structure Discovery**
   - Identify project type (language, framework)
   - Map directory structure
   - Locate configuration files
   - Find entry points

2. **Dependency Analysis**
   - External dependencies (package.json, requirements.txt, go.mod, etc.)
   - Internal module dependencies
   - Circular dependency detection

3. **Pattern Identification**
   - Architectural pattern in use (layered, hexagonal, etc.)
   - Design patterns observed
   - Coding conventions

4. **Issue Detection**
   - God classes/modules (too many responsibilities)
   - Tight coupling indicators
   - Missing abstractions
   - Inconsistent patterns

## Output Format

```
## Architecture Analysis: [project-name]

### Overview
- Type: [language/framework]
- Pattern: [architectural pattern]
- Size: [files/LOC estimate]

### Structure
[Directory tree with annotations]

### Key Components
| Component | Responsibility | Dependencies |
|-----------|---------------|--------------|
| ...       | ...           | ...          |

### Patterns Observed
- [pattern]: [where used]

### Issues Found
1. **[Issue]**: [description] - Severity: [high/medium/low]
   - Location: [file:line]
   - Suggestion: [fix]

### Recommendations
1. [Prioritized improvement]
```

Focus on actionable findings. Skip obvious or trivial observations.
