# diagrams-as-code

C4 model diagrams with proper abstraction levels. Supports PlantUML, Mermaid, D2, and Structurizr DSL.

## Commands

| Command | Description |
|---------|-------------|
| `/diagram <type> [format]` | Architecture diagrams with purpose-driven selection |
| `/c4-diagram <level>` | C4 diagrams: Context, Container, Component, Deployment, Dynamic |
| `/diagram-from-code <type> [dir]` | Generate diagrams from existing code |

## Agent

**diagram-assistant** - Architecture visualization expert. Understands C4 abstraction discipline and selects appropriate diagram types for communication goals.

## Skill

**diagram-generation** - Activates when generating architecture diagrams. Brings knowledge of C4 model, diagram syntax, and visualization best practices.

## C4 Model Levels

| Level | Purpose | Audience |
|-------|---------|----------|
| Context | System scope and external actors | Everyone |
| Container | Deployable units and technology | Technical staff |
| Component | Internal structure of containers | Developers |
| Code | Class/module details | Developers |
| Deployment | Infrastructure mapping | DevOps |
| Dynamic | Runtime interactions | Technical staff |

## Supported Formats

- **PlantUML** (recommended for C4) - Full C4 library support
- **Mermaid** - Good for documentation
- **D2** - Clean presentations
- **Structurizr DSL** - Architecture-as-code

## Usage

```
/c4-diagram container

"Show the container diagram for our e-commerce platform
with the payment gateway and inventory integrations."
```

Generates properly structured C4 diagrams with correct notation, relationships, and technology annotations.
