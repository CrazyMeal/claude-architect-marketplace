---
description: Generate C4 model diagrams (Context, Container, Component, Code)
argument-hint: <level> [system-name]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# C4 Model Diagram Generation

Generate C4 architecture diagrams.

## C4 Levels

1. **context**: System context - system + external actors/systems
2. **container**: Containers - applications, data stores, services
3. **component**: Components within a container
4. **code**: Code level (typically class diagrams)

## Process

1. **Determine scope**: What system/container to diagram
2. **Identify elements** at the appropriate level
3. **Map relationships** and data flows
4. **Generate in PlantUML** (best C4 support) or Mermaid

## Output Format (PlantUML C4)

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml

title System Context diagram for [System]

Person(user, "User", "Description")
System(system, "System", "Description")
System_Ext(external, "External System", "Description")

Rel(user, system, "Uses")
Rel(system, external, "Calls")

@enduml
```

## Guidelines

- One diagram per level
- Keep descriptions concise (< 50 chars)
- Show only relevant relationships
- Use consistent naming across levels
- Include legend for complex diagrams
