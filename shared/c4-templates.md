# C4 Diagram Templates

## C4 Philosophy
- Each level zooms into a specific aspect
- Don't mix abstraction levels in one diagram
- Same element = same name across all diagrams
- Describe what flows, not just that things connect

## Level 1: Context
**Purpose**: System scope and external interactions
**Audience**: All stakeholders

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml

title System Context: [System Name]

Person(user, "User Type", "Role description")
System(system, "System Name", "Value proposition")
System_Ext(external, "External System", "What it provides")

Rel(user, system, "Uses", "Protocol")
Rel(system, external, "Depends on", "Protocol")

SHOW_LEGEND()
@enduml
```

## Level 2: Container
**Purpose**: Deployable units and technology choices
**Audience**: Technical stakeholders

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

title Container Diagram: [System Name]

Person(user, "User", "Description")

System_Boundary(sys, "System Name") {
    Container(web, "Web App", "React", "User interface")
    Container(api, "API", "Go", "Business logic")
    ContainerDb(db, "Database", "PostgreSQL", "Persistence")
    ContainerQueue(queue, "Queue", "Kafka", "Events")
}

System_Ext(ext, "External System", "Third party")

Rel(user, web, "Uses", "HTTPS")
Rel(web, api, "Calls", "REST")
Rel(api, db, "Reads/Writes", "SQL")
Rel(api, queue, "Publishes")
Rel(api, ext, "Integrates", "API")

SHOW_LEGEND()
@enduml
```

## Level 3: Component
**Purpose**: Internal structure of a container
**Audience**: Developers

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Component.puml

title Component Diagram: [Container Name]

Container_Boundary(api, "API Application") {
    Component(ctrl, "Controllers", "Go", "HTTP handlers")
    Component(svc, "Services", "Go", "Business logic")
    Component(repo, "Repositories", "Go", "Data access")
    Component(domain, "Domain", "Go", "Business rules")
}

ContainerDb(db, "Database", "PostgreSQL")

Rel(ctrl, svc, "Uses")
Rel(svc, domain, "Uses")
Rel(svc, repo, "Uses")
Rel(repo, db, "Queries")

SHOW_LEGEND()
@enduml
```

## Deployment Diagram
```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Deployment.puml

title Deployment: [Environment]

Deployment_Node(cloud, "Cloud Provider", "AWS/GCP/Azure") {
    Deployment_Node(k8s, "Kubernetes", "EKS/GKE/AKS") {
        Container(api, "API", "Container")
    }
    Deployment_Node(db, "Managed DB", "RDS/CloudSQL") {
        ContainerDb(database, "Database", "PostgreSQL")
    }
}

Rel(api, database, "Connects", "TLS")
@enduml
```

## Dynamic Diagram (Sequence)
```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Dynamic.puml

title Dynamic: [Scenario Name]

Container(web, "Web", "React")
Container(api, "API", "Go")
ContainerDb(db, "Database", "PostgreSQL")

Rel(web, api, "1. POST /resource", "REST")
Rel(api, db, "2. INSERT", "SQL")
Rel(api, web, "3. 201 Created", "JSON")
@enduml
```

## File Naming Convention
```
docs/diagrams/
├── c4-context-[system].puml
├── c4-container-[system].puml
├── c4-component-[container].puml
├── c4-deployment-[env].puml
├── c4-dynamic-[scenario].puml
├── seq-[flow].puml
├── activity-[process].puml
└── domain-[context].puml
```

## DDD Stereotypes for Domain Models
`<<Aggregate Root>>`, `<<Entity>>`, `<<Value Object>>`, `<<Domain Event>>`, `<<Repository>>`, `<<Domain Service>>`
