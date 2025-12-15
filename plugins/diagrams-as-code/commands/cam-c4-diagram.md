---
description: Generate C4 model diagrams with proper abstraction levels and notation
argument-hint: <level> [scope]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# C4 Model Diagrams

Generate C4 architecture diagrams following Simon Brown's C4 model principles.

## C4 Philosophy

The C4 model is about **abstraction levels**, not just diagram types:
- Each level zooms into a specific aspect
- Skip levels that don't add value for your context
- Supplement with other diagram types as needed

## Level 1: System Context

**Purpose**: Show system scope and external interactions
**Audience**: Everyone - technical and non-technical stakeholders
**Content**: Your system as a box, users, and external system dependencies

**Key decisions**:
- What's inside vs outside your system boundary?
- Who are the primary user types?
- What external systems are critical dependencies?

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml

title System Context: [System Name]

Person(user, "User Type", "Brief description of user role")
System(system, "System Name", "Value proposition in one sentence")
System_Ext(external, "External System", "What it provides")

Rel(user, system, "Uses", "Protocol if relevant")
Rel(system, external, "Depends on", "Protocol if relevant")

SHOW_LEGEND()
@enduml
```

## Level 2: Container

**Purpose**: Show high-level technology choices and deployment units
**Audience**: Technical stakeholders, developers
**Content**: Applications, databases, message queues, file systems

**Key decisions**:
- What are the separately deployable/runnable units?
- What are the major technology choices?
- How do containers communicate?

**Container types**:
- `Container`: Custom-built application
- `ContainerDb`: Database
- `ContainerQueue`: Message queue/broker
- `Container_Ext`: External container you don't control

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

title Container Diagram: [System Name]

Person(user, "User", "Description")

System_Boundary(system, "System Name") {
    Container(web, "Web Application", "React, TypeScript", "Provides UI")
    Container(api, "API", "Go", "Handles business logic")
    ContainerDb(db, "Database", "PostgreSQL", "Stores data")
    ContainerQueue(queue, "Message Queue", "RabbitMQ", "Async processing")
}

System_Ext(external, "External API", "Third-party service")

Rel(user, web, "Uses", "HTTPS")
Rel(web, api, "Calls", "REST/JSON")
Rel(api, db, "Reads/Writes", "SQL")
Rel(api, queue, "Publishes to")
Rel(api, external, "Calls", "HTTPS")

SHOW_LEGEND()
@enduml
```

## Level 3: Component

**Purpose**: Show internal structure of a container
**Audience**: Developers working on that container
**Content**: Major structural building blocks (not every class)

**Key decisions**:
- What are the major components/modules?
- How are responsibilities divided?
- What patterns are in use (MVC, Hexagonal, etc.)?

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Component.puml

title Component Diagram: [Container Name]

Container_Boundary(api, "API Application") {
    Component(controller, "Controllers", "Go", "HTTP handlers")
    Component(service, "Services", "Go", "Business logic")
    Component(repo, "Repositories", "Go", "Data access")
    Component(domain, "Domain", "Go", "Core business rules")
}

ContainerDb(db, "Database", "PostgreSQL")
ContainerQueue(queue, "Queue", "RabbitMQ")

Rel(controller, service, "Uses")
Rel(service, domain, "Uses")
Rel(service, repo, "Uses")
Rel(repo, db, "Queries")
Rel(service, queue, "Publishes")

SHOW_LEGEND()
@enduml
```

## Level 4: Code

Typically UML class diagrams - often auto-generated from code.
Only create manually when explaining critical domain model or complex patterns.

## Supplementary Diagrams

C4 recommends adding these as needed:

### Dynamic Diagram
Show specific scenarios/flows through the containers:
```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Dynamic.puml

title Dynamic Diagram: [Scenario Name]

ContainerDb(db, "Database", "PostgreSQL")
Container(api, "API", "Go")
Container(web, "Web", "React")

Rel(web, api, "1. POST /orders", "REST")
Rel(api, db, "2. Insert order", "SQL")
Rel(api, web, "3. Order confirmation", "JSON")

@enduml
```

### Deployment Diagram
Show how containers map to infrastructure:
```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Deployment.puml

title Deployment Diagram: [Environment]

Deployment_Node(aws, "AWS", "Cloud") {
    Deployment_Node(eks, "EKS", "Kubernetes") {
        Container(api, "API", "Go container")
    }
    Deployment_Node(rds, "RDS", "Managed PostgreSQL") {
        ContainerDb(db, "Database", "PostgreSQL")
    }
}

Rel(api, db, "Connects", "TLS")

@enduml
```

## Best Practices

1. **Abstraction discipline**: Don't mix abstraction levels
2. **Consistent naming**: Same element has same name across diagrams
3. **Technology annotations**: Include tech choices at Container level
4. **Relationship labels**: Describe what flows, not just that there's a connection
5. **Living documentation**: Keep diagrams updated with architecture
