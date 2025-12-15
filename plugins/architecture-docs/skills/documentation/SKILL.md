---
name: documentation
description: Create and improve architecture documentation. Activates when discussing ADRs, specs, RFCs, or any architecture documentation needs.
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Architecture Documentation

Create effective documentation that captures decisions, designs, and operational knowledge.

## Activation Contexts

- Documenting architectural decisions
- Creating technical specifications
- Writing RFCs for proposals
- Generating C4 documentation
- Creating runbooks
- Reviewing existing documentation

## Document Selection

| Need | Document Type | Key Characteristics |
|------|--------------|---------------------|
| Record a decision | ADR | MADR format, alternatives, consequences |
| Design a feature | Tech Spec | Problem-first, quality attributes, operations |
| Propose major change | RFC | Motivation, approach, discussion |
| Explain the system | Architecture Doc | C4 levels, key decisions |
| Enable operations | Runbook | Procedures, commands, contacts |

## ADR Approach

When creating ADRs:

1. **Identify the decision**: One ADR = one decision
2. **Gather drivers**: What forces led to this decision?
3. **Document options**: Including rejected ones
4. **Capture consequences**: Both positive and negative
5. **Link related ADRs**: Decisions form a web

MADR structure:
- Status, Date, Decision Makers
- Context and Problem Statement
- Decision Drivers
- Considered Options
- Decision Outcome with Consequences
- Pros/Cons of Each Option
- Links

## Specification Approach

When creating tech specs:

1. **Start with problem**: What are we solving? Why now?
2. **Define quality attributes**: Measurable requirements
3. **Design the solution**: Architecture, data, APIs
4. **Address operations**: Deployment, monitoring, failure modes
5. **Identify risks**: What could go wrong?
6. **Plan implementation**: Phases, migration, flags

## Documentation Principles

### Right-size the documentation
- ADR: Concise (1-2 pages)
- Tech Spec: Comprehensive (5-15 pages)
- RFC: Thorough but focused

### Make it scannable
- Clear headers
- Bullet points and tables
- Code blocks for technical details
- Diagrams for architecture

### Keep it current
- Update when things change
- Mark obsolete sections
- Link to source of truth

### Connect the docs
- ADRs reference each other
- Specs link to ADRs
- All docs link to code when relevant

## Quality Checklist

Before completing documentation:
- [ ] Clear purpose stated upfront
- [ ] Audience can understand without external context
- [ ] Trade-offs explicitly documented
- [ ] Alternatives considered and explained
- [ ] Next steps or action items clear
- [ ] Related documents linked
- [ ] Diagrams support the text
