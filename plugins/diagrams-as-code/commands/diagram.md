---
description: Generate architecture diagrams with proper notation and purpose alignment
argument-hint: <type> [format] [output-file]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Diagram Generation

Generate architecture diagrams with proper notation.

## Diagram Types

| Type | Use For | Recommended Format |
|------|---------|-------------------|
| context | System scope, actors | PlantUML C4 |
| container | Deployables, tech | PlantUML C4 |
| component | Internal structure | PlantUML C4 |
| sequence | Interactions over time | PlantUML/Mermaid |
| activity | Business processes | Mermaid |
| state | Entity lifecycles | Mermaid |
| er | Data relationships | Mermaid |
| domain | DDD class diagram | PlantUML/Mermaid |
| deployment | Infrastructure | PlantUML C4 |

## Format Selection

| Format | Best For |
|--------|----------|
| PlantUML | C4 diagrams, UML, detailed diagrams |
| Mermaid | Markdown docs, simple diagrams, GitHub rendering |
| D2 | Presentations, modern aesthetics |

## Workflow

1. **Understand purpose**: What should viewer learn?
2. **Select type**: Based on what's being communicated
3. **Select format**: Based on output needs
4. **Generate**: With proper notation
5. **Write to file**: `docs/diagrams/[type]-[name].[ext]`

## Output

Reference `shared/c4-templates.md` for C4 syntax.
Reference `references/syntax-reference.md` for Mermaid/D2.

Write to `docs/diagrams/` with descriptive names.
