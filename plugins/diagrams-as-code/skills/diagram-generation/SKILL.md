---
name: diagram-generation
description: Generate architecture diagrams automatically. Use when users discuss system structure, ask for visualizations, or need documentation diagrams.
allowed-tools: Read, Grep, Glob, Write
---

# Diagram Generation Skill

Automatically generate appropriate diagrams when users discuss architecture.

## Activation Triggers

- Requests for visual representation
- Discussion of system structure
- Component interaction explanations
- Documentation creation
- Mentions of "diagram", "flowchart", "sequence", "architecture"

## Response Approach

1. **Identify diagram need** from conversation context
2. **Select appropriate type**:
   - Interactions → Sequence diagram
   - Structure → Component/Class diagram
   - Flow → Flowchart
   - Data → ER diagram
   - System overview → C4 Context

3. **Generate in Mermaid** (default, most portable)
4. **Offer alternatives** if Mermaid insufficient

## Output Template

When generating diagrams, provide:

```mermaid
[diagram code]
```

This diagram shows [brief explanation].

To render: [instructions if needed]

## Constraints

- Max 20 nodes per diagram
- Use meaningful, short labels
- Prefer horizontal layouts for sequences
- Prefer vertical for hierarchies
- Include diagram type in code fence
