# Diagram Syntax Reference

## Mermaid

### Flowchart
```mermaid
flowchart TD
    A[Start] --> B{Decision}
    B -->|Yes| C[Action]
    B -->|No| D[Other]
```

### Sequence
```mermaid
sequenceDiagram
    participant A as Service A
    participant B as Service B
    A->>B: Request
    B-->>A: Response
```

### ER
```mermaid
erDiagram
    USER ||--o{ ORDER : places
    ORDER ||--|{ ITEM : contains
```

### State
```mermaid
stateDiagram-v2
    [*] --> Draft
    Draft --> Review
    Review --> Approved
    Review --> Draft
    Approved --> [*]
```

## PlantUML C4

Reference `shared/c4-templates.md` for full C4 templates.

Quick reference:
```plantuml
@startuml
!include C4_Container.puml
Person(user, "User")
Container(app, "App", "Tech", "Desc")
Rel(user, app, "Uses")
@enduml
```

## D2

```d2
server: Web Server
db: Database
server -> db: queries
```

## Shape Reference (Mermaid)

| Syntax | Shape |
|--------|-------|
| [text] | Rectangle |
| (text) | Rounded |
| {text} | Diamond |
| ([text]) | Stadium |
| [(text)] | Cylinder |

## Arrow Reference

| Mermaid | PlantUML | Meaning |
|---------|----------|---------|
| --> | -> | Solid |
| -.-> | ..> | Dashed |
| -->> | ->> | Async |
