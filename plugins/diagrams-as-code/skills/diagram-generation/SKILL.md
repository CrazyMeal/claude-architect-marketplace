---
name: diagram-generation
description: Generate architecture diagrams as code. Use this skill whenever the user discusses system structure, wants to visualize components or flows, creates documentation, or asks for any kind of architecture diagram -- including C4, sequence, activity, ER, or deployment diagrams. Applies C4 thinking to maintain proper abstraction levels.
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Diagram Generation

Create effective architecture visualizations during technical discussions. A good diagram communicates what paragraphs of text cannot -- spatial relationships, boundaries, and flow direction.

## Activation Contexts

- Discussing system structure or components
- Explaining system interactions or flows
- Creating or reviewing documentation
- Onboarding discussions about how things work
- Planning new features or systems

## Diagram Selection

| Discussion Topic | Diagram Type | Format | Why This Type |
|-----------------|--------------|--------|---------------|
| System scope & external actors | C4 Context | PlantUML | Shows what the system is and who/what it interacts with |
| Tech stack & deployables | C4 Container | PlantUML | Shows the major technical building blocks and how they communicate |
| Internal structure of a container | C4 Component | PlantUML | Shows the components inside a single container |
| "What happens when..." | Sequence | PlantUML/Mermaid | Shows the order of interactions between participants |
| Business process flow | Activity | Mermaid | Shows decision points and parallel paths in a process |
| Entity lifecycle | State | Mermaid | Shows the valid states and transitions for an entity |
| Data structure & relationships | ER/Domain | Mermaid | Shows entities, attributes, and how they relate |
| Infrastructure mapping | Deployment | PlantUML | Shows how containers map to infrastructure |

### Choosing Between PlantUML and Mermaid

Use **PlantUML** for C4 diagrams -- the C4-PlantUML library provides proper stereotypes, boundaries, and legends that Mermaid lacks. Also prefer PlantUML for deployment diagrams where nesting and grouping matter.

Use **Mermaid** for diagrams in markdown-rendered contexts (GitHub, GitLab READMEs) where PlantUML rendering isn't available, and for simpler diagrams (flowcharts, ER, state) where C4 abstraction levels don't apply.

When in doubt, ask what the user's rendering environment supports.

## C4 Model Application

Read `shared/c4-templates.md` for PlantUML syntax and templates.

Key principles:
1. **Identify the abstraction level first** -- are we talking about the whole system (Context), the major containers (Container), or internals of one container (Component)?
2. **Never mix abstraction levels** -- showing a database table detail (Level 3) in a system context diagram (Level 1) confuses the audience about what level of decision is being made.
3. **Name consistently across diagrams** -- the "Payment Service" in the Context diagram must be the same "Payment Service" in the Container diagram. Inconsistent naming erodes trust in the documentation.
4. **Label what flows, not just connections** -- "Sends order confirmation email" tells the reader what business value crosses the boundary. "Calls" or "uses" tells them nothing.

## Generation Approach

1. **Clarify purpose**: What should the viewer understand after seeing this diagram? A diagram without a clear communication goal is decoration.
2. **Identify audience**: Executives need Context level. Developers need Container or Component level. Match technical depth to who's reading.
3. **Scope tightly**: Include only what's needed to communicate the point. Resist the urge to show everything -- a diagram with 20+ elements overwhelms rather than clarifies.
4. **Select format**: PlantUML for C4 and complex diagrams; Mermaid for markdown contexts and simpler visualizations.
5. **One diagram, one message**: Each diagram should communicate exactly one thing well. If you need to show both the deployment topology and the request flow, make two diagrams.

## Quality Checks

Before finalizing a diagram, verify:
- [ ] **Single clear purpose** -- can you state in one sentence what this diagram shows?
- [ ] **Appropriate abstraction level** -- no mixing of levels
- [ ] **Meaningful labels** -- relationship labels answer "what business value crosses this boundary?" not just "calls" or "sends"
- [ ] **7±2 elements** -- more than ~9 elements needs grouping or splitting into multiple diagrams
- [ ] **Consistent notation** -- same shapes/colors mean the same things

## When Not to Diagram

- **Simple enough for words** -- if a one-sentence description is clearer, don't force a visual. "Service A calls Service B's REST API" doesn't need a diagram.
- **Will be immediately outdated** -- if the design is changing daily, a diagram creates false confidence. Wait until the design stabilizes.
- **No clear audience** -- who will read this? If the answer is "nobody specific," the diagram will rot unread.
- **Still exploring options** -- rough sketches are fine, but polished diagrams for uncommitted designs waste effort. Use whiteboard-style notes instead.
- **Duplicates an existing diagram** -- check `docs/diagrams/` before creating. Update existing diagrams rather than creating parallel versions.
