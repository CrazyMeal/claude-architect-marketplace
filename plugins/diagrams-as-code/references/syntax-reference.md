# Diagram Syntax Quick Reference

## Mermaid

### Flowchart
```mermaid
flowchart TD
    A[Start] --> B{Decision}
    B -->|Yes| C[Action 1]
    B -->|No| D[Action 2]
    C --> E[End]
    D --> E
```

### Sequence
```mermaid
sequenceDiagram
    participant A as Service A
    participant B as Service B
    A->>B: Request
    B-->>A: Response
```

### Class
```mermaid
classDiagram
    class Animal {
        +String name
        +makeSound()
    }
    class Dog {
        +bark()
    }
    Animal <|-- Dog
```

### ER
```mermaid
erDiagram
    USER ||--o{ ORDER : places
    ORDER ||--|{ ITEM : contains
```

## PlantUML C4

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

## Shape Reference

| Mermaid | Meaning |
|---------|---------|
| [text] | Rectangle |
| (text) | Rounded |
| {text} | Diamond |
| ([text]) | Stadium |
| [[text]] | Subroutine |
| [(text)] | Cylinder |

## Arrow Reference

| Mermaid | PlantUML | Meaning |
|---------|----------|---------|
| --> | -> | Solid line |
| -.-> | ..> | Dashed line |
| -->> | ->> | Async/return |
