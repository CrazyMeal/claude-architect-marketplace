---
description: Design a new software system architecture from requirements
argument-hint: <system-name> [requirements-file]
allowed-tools: Read, Grep, Glob, Write
model: sonnet
---

# System Architecture Design

You are designing a software system architecture. Follow this structured approach:

## Process

1. **Clarify Requirements**: If a requirements file is provided, read it. Otherwise, ask for:
   - Core functionality and use cases
   - Scale expectations (users, data volume, throughput)
   - Non-functional requirements (latency, availability, consistency)
   - Constraints (budget, timeline, team expertise, existing systems)

2. **Identify Components**: Break down into:
   - Core services/modules
   - Data stores
   - External integrations
   - Infrastructure components

3. **Define Interactions**: For each component pair:
   - Communication pattern (sync/async, REST/gRPC/events)
   - Data flow direction
   - Failure handling

4. **Document Decisions**: For key choices, note:
   - Decision made
   - Alternatives considered
   - Rationale

## Output Format

Produce a structured design document with:
- **Overview**: 2-3 sentence system summary
- **Components**: Table of components with responsibilities
- **Interactions**: Key flows described concisely
- **Data Model**: Core entities and relationships
- **Key Decisions**: Numbered list with rationale
- **Risks**: Top 3 architectural risks
- **Next Steps**: Concrete action items

Keep output focused and actionable. Avoid verbose explanations.
