---
description: Generate diagram from existing codebase structure
argument-hint: <diagram-type> [directory] [output-file]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# Diagram from Code

Generate architecture diagrams by analyzing existing code structure.

## Supported Diagram Types

| Type | What's Analyzed |
|------|-----------------|
| container | Package/module structure → deployables |
| component | Classes/modules → internal structure |
| dependencies | Import statements → dependency graph |
| domain | DDD patterns → domain model |
| er | Models/schemas → entity relationships |

## Analysis Approach

### For Container Diagram
1. Identify main packages/modules
2. Detect entry points (main, handlers)
3. Find infrastructure (DB, queue, cache)
4. Map external integrations

### For Component Diagram
1. Identify major classes/modules
2. Detect patterns (controller, service, repository)
3. Map internal dependencies
4. Identify layer boundaries

### For Domain Model
1. Find aggregate roots
2. Identify entities vs value objects
3. Detect domain events
4. Map relationships

### For Dependencies
1. Parse import/require statements
2. Build dependency graph
3. Identify circular dependencies
4. Calculate coupling metrics

## Output Format

Generate PlantUML for C4/component, Mermaid for ER/dependency.

Include:
- Diagram title
- Elements discovered
- Relationships with labels
- Notes on assumptions

Write to `docs/diagrams/[type]-[name]-discovered.[ext]`
