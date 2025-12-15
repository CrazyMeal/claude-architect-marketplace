---
name: diagram-generation
description: Generate architecture diagrams when discussing system structure, flows, or documentation needs. Applies C4 model thinking and proper notation.
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Diagram Generation

Create effective architecture visualizations during technical discussions.

## Activation Contexts

- Discussing system structure or components
- Explaining how systems interact
- Creating or reviewing documentation
- Onboarding discussions about architecture
- Planning new features or systems
- Requests for visualizations

## Diagram Selection Logic

Based on conversation context:

| Discussion Topic | Diagram Type | Format |
|-----------------|--------------|--------|
| System scope, boundaries | C4 Context | PlantUML |
| Tech stack, deployables | C4 Container | PlantUML |
| Internal structure | C4 Component | PlantUML |
| "What happens when..." | Sequence | Mermaid or PlantUML |
| Business process | Activity/Flowchart | Mermaid |
| Entity lifecycle | State diagram | Mermaid |
| Data structure | ER or Domain model | Mermaid |
| Infrastructure | Deployment | PlantUML |

## C4 Model Application

Apply C4 thinking even in informal discussions:

1. **Identify abstraction level**: Are we talking systems, containers, or components?
2. **Respect boundaries**: Don't mix abstraction levels in one diagram
3. **Name consistently**: Same element, same name everywhere
4. **Show relationships**: What flows between elements, not just that they connect

## Generation Approach

1. **Clarify purpose**: What should viewers understand after seeing this?
2. **Identify audience**: Technical depth appropriate for viewers
3. **Scope appropriately**: Include only what's needed for the purpose
4. **Select format**: Mermaid for docs, PlantUML for C4, D2 for presentations
5. **Keep focused**: One diagram, one message

## Output Format

When generating diagrams:

```
## [Diagram Title]

**Purpose**: [What this communicates]
**Audience**: [Who this is for]

[Diagram code block]

**Key takeaways**:
- [Main insight 1]
- [Main insight 2]

**Related views**: [Other diagrams that complement this]
```

## Quality Checks

Before presenting a diagram, verify:
- [ ] Single clear purpose
- [ ] Appropriate abstraction level
- [ ] Meaningful labels (not just "calls" or "uses")
- [ ] 7±2 elements (or clearly grouped)
- [ ] Consistent notation

## When Not to Diagram

- Simple enough to explain in words
- Will be outdated immediately
- No clear audience
- Premature (still exploring options)
