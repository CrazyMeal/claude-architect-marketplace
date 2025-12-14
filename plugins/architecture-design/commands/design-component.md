---
description: Design a specific component or module within a larger system
argument-hint: <component-name> [context-file]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# Component Design

Design a specific component within a larger system architecture.

## Process

1. **Understand Context**: Read any provided context file or existing architecture docs
2. **Define Boundaries**: Clarify what this component owns vs. delegates
3. **Design Interface**: Public API, events emitted, dependencies required
4. **Internal Structure**: Key classes/modules and their responsibilities
5. **State Management**: What state this component manages and how

## Output Format

```
## Component: [name]

### Responsibility
Single sentence describing what this component does.

### Interface
- Inputs: [list methods/events consumed]
- Outputs: [list methods/events produced]
- Dependencies: [list required services/modules]

### Internal Structure
[List of internal modules with one-line descriptions]

### Data Owned
[Tables/collections this component manages]

### Error Handling
[How failures are handled and communicated]

### Configuration
[Required configuration parameters]
```

Be precise. Avoid implementation details unless architecturally significant.
