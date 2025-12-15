---
description: Generate diagram from existing codebase structure
argument-hint: <diagram-type> [directory] [output-file]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# Diagram from Code

Analyze code and generate architectural diagrams.

## Diagram Types

- **module**: Module/package dependencies
- **class**: Class relationships (inheritance, composition)
- **flow**: Request/data flow through system
- **layer**: Architectural layers
- **component**: High-level component view

## Process

1. **Scan codebase** structure and imports
2. **Identify relationships** between modules/classes
3. **Generate diagram** in Mermaid format (most portable)
4. **Save if output path provided**

## Output Format

```mermaid
[generated diagram]
```

**Components shown:**
- [list of key elements]

**Relationships:**
- [summary of connections]

**Notes:**
- [any simplifications made]

## Guidelines

- Limit to ~15-20 nodes per diagram for readability
- Group related items
- Exclude trivial dependencies (utils, common)
- Use meaningful labels, not file paths
