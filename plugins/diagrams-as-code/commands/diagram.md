---
description: Generate architecture diagrams with proper notation and purpose alignment
argument-hint: <type> [format] [output-file]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Architecture Diagram Generation

Create diagrams that communicate effectively to their intended audience.

## Diagram Type Selection

Choose based on what you're communicating:

### Structural Diagrams
| Type | Purpose | Audience | Key Elements |
|------|---------|----------|--------------|
| C4 Context | System boundaries, external actors | Stakeholders, new team members | System, users, external systems |
| C4 Container | Deployment units, tech choices | Architects, developers | Apps, databases, message queues |
| C4 Component | Internal structure | Developers | Classes, modules, their relationships |
| Deployment | Infrastructure mapping | Ops, architects | Nodes, containers, network topology |

### Behavioral Diagrams
| Type | Purpose | When to Use |
|------|---------|-------------|
| Sequence | Show interactions over time | API flows, complex handoffs, debugging |
| Activity/Flow | Show decision logic | Business processes, workflows |
| State Machine | Show lifecycle | Entity states, protocol states |

### Data Diagrams
| Type | Purpose | Key Considerations |
|------|---------|-------------------|
| ER Diagram | Data relationships | Show cardinality, key entities only |
| Domain Model | Conceptual entities | Focus on ubiquitous language |

## Format Selection

### Mermaid
**Strengths**: GitHub/GitLab native, simple syntax, good for docs
**Limitations**: Less control over layout, limited C4 support
**Use when**: Documentation in repos, quick communication

### PlantUML
**Strengths**: Full C4 library, extensive features, consistent rendering
**Limitations**: Requires tooling, verbose syntax
**Use when**: Formal architecture docs, C4 diagrams, complex sequences

### D2
**Strengths**: Modern syntax, beautiful defaults, easy to read
**Limitations**: Newer tool, less adoption
**Use when**: Presentations, clean system overviews

### Structurizr DSL
**Strengths**: Purpose-built for C4, model-once-render-many
**Limitations**: Specific tooling required
**Use when**: Living documentation, architecture-as-code

## Diagram Principles

### Cognitive Load
- **7±2 rule**: Limit elements per diagram
- **Hierarchy**: Use zoom levels (C4 approach)
- **Chunking**: Group related elements

### Notation Consistency
- Same element = same shape everywhere
- Color for meaning, not decoration
- Legend when non-obvious notation used

### Maintainability
- Prefer generated from code/model when possible
- Store diagram source in version control
- Keep descriptions in diagram, not just accompanying text

## Output Approach

1. Clarify what needs to be communicated and to whom
2. Select appropriate diagram type for the message
3. Choose format based on rendering context
4. Generate focused diagram (split if too complex)
5. Provide rendering instructions if needed

```
## Diagram: [title]

### Purpose
[What this diagram communicates and to whom]

### Diagram
[code block with diagram]

### Key Insights
[What viewers should take away]

### Related Diagrams
[Other views that complement this one]
```
