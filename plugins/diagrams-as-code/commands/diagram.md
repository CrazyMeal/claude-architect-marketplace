---
description: Generate an architecture diagram in specified format (mermaid, plantuml, d2)
argument-hint: <type> <format> [output-file]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# Diagram Generation

Generate architecture diagrams as code.

## Arguments

- **type**: flowchart | sequence | class | er | c4-context | c4-container | c4-component | state | deployment
- **format**: mermaid | plantuml | d2
- **output-file**: Optional path to save the diagram

## Process

1. **Gather context**: Ask what to diagram or read existing docs/code
2. **Select appropriate diagram type** if not specified
3. **Generate diagram code** in requested format
4. **Save to file** if output path provided

## Format Guidelines

### Mermaid
- Use for GitHub/GitLab rendering, Markdown docs
- Simpler syntax, fewer features
- Good for: flowcharts, sequence, ER, class diagrams

### PlantUML
- Use for detailed technical diagrams
- Rich feature set, more verbose
- Good for: C4, deployment, complex sequences

### D2
- Use for modern, clean diagrams
- Declarative syntax, automatic layout
- Good for: system overviews, flowcharts

## Output

Provide:
1. The diagram code in a code block with appropriate language tag
2. Brief explanation of what it shows
3. Rendering instructions if not obvious

Keep diagrams focused. Split complex systems into multiple diagrams.
