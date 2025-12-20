---
description: Generate C4 model diagrams with proper abstraction levels
argument-hint: <level> [scope]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# C4 Model Diagrams

Generate C4 architecture diagrams following Simon Brown's model.

## C4 Philosophy

Abstraction levels, not just diagram types:
- Each level zooms into a specific aspect
- Skip levels that don't add value
- Supplement with dynamic/deployment as needed

## Levels

### Level 1: Context
**Purpose**: System scope, external interactions
**Audience**: All stakeholders
**Content**: System box, users, external dependencies

### Level 2: Container
**Purpose**: Deployables, tech choices
**Audience**: Technical stakeholders
**Content**: Apps, databases, queues, external containers

### Level 3: Component
**Purpose**: Internal structure of one container
**Audience**: Developers
**Content**: Major structural blocks (not every class)

### Level 4: Code
Typically auto-generated. Manual only for critical domain models.

### Supplementary
- **Dynamic**: Specific scenarios through containers
- **Deployment**: Containers mapped to infrastructure

## Syntax

Reference `shared/c4-templates.md` for PlantUML templates.

## Best Practices

1. **Abstraction discipline**: Don't mix levels
2. **Consistent naming**: Same element, same name
3. **Technology annotations**: At Container level
4. **Relationship labels**: What flows, not just "calls"
5. **Living documentation**: Keep updated

## Output

Write to `docs/diagrams/c4-[level]-[name].puml`
