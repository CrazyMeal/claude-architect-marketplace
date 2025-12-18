---
name: diagram-generation
description: Generate architecture diagrams when discussing system structure, flows, or documentation. Applies C4 thinking.
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Diagram Generation

Create effective architecture visualizations during technical discussions.

## Activation Contexts

- Discussing system structure or components
- Explaining system interactions
- Creating or reviewing documentation
- Onboarding discussions
- Planning new features or systems

## Diagram Selection

| Discussion Topic | Diagram Type | Format |
|-----------------|--------------|--------|
| System scope | C4 Context | PlantUML |
| Tech stack | C4 Container | PlantUML |
| Internal structure | C4 Component | PlantUML |
| "What happens when..." | Sequence | PlantUML/Mermaid |
| Business process | Activity | Mermaid |
| Entity lifecycle | State | Mermaid |
| Data structure | ER/Domain | Mermaid |
| Infrastructure | Deployment | PlantUML |

## C4 Model Application

Reference `shared/c4-templates.md` for syntax.

Key principles:
1. Identify abstraction level
2. Respect boundaries (don't mix levels)
3. Name consistently across diagrams
4. Show what flows, not just connections

## Generation Approach

1. **Clarify purpose**: What should viewers understand?
2. **Identify audience**: Appropriate technical depth
3. **Scope**: Include only what's needed
4. **Select format**: PlantUML for C4, Mermaid for markdown docs
5. **Keep focused**: One diagram, one message

## Quality Checks

Before finalizing:
- [ ] Single clear purpose
- [ ] Appropriate abstraction level
- [ ] Meaningful labels (not just "calls")
- [ ] 7±2 elements (or grouped)
- [ ] Consistent notation

## When Not to Diagram

- Simple enough for words
- Will be immediately outdated
- No clear audience
- Still exploring options
