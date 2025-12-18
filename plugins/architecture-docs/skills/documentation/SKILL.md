---
name: documentation
description: Create and improve architecture documentation. Activates for ADRs, specs, RFCs, or documentation needs.
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Architecture Documentation

Create effective documentation that captures decisions, designs, and operational knowledge.

## Activation Contexts

- Documenting architectural decisions
- Creating technical specifications
- Writing RFCs for proposals
- Creating C4 documentation
- Reviewing existing documentation

## Document Selection

| Need | Document Type | Key Characteristics |
|------|--------------|---------------------|
| Record a decision | ADR | MADR format, alternatives, consequences |
| Design a feature | Tech Spec | Problem-first, QAs, operations |
| Propose major change | RFC | Motivation, proposal, discussion |
| Explain the system | Architecture Doc | C4 levels, key decisions |
| Enable operations | Runbook | Procedures, commands, contacts |

## ADR Approach

1. Identify: One ADR = one decision
2. Gather drivers: What forces led here?
3. Document options: Including rejected
4. Capture consequences: Positive and negative
5. Link related ADRs

## Spec Approach

1. Start with problem: What and why now?
2. Define QAs: Measurable requirements
3. Design solution: Architecture, data, APIs
4. Address operations: Deployment, monitoring, failures
5. Plan implementation: Phases, migration

## Documentation Principles

- **Right-size**: Match document length to decision scope
- **Scannable**: Headers, bullets, tables, diagrams
- **Current**: Update when things change
- **Connected**: Cross-reference related docs

## Quality Checklist

- [ ] Clear purpose upfront
- [ ] Self-contained (no external context needed)
- [ ] Trade-offs documented
- [ ] Alternatives explained
- [ ] Next steps clear
- [ ] Related docs linked
- [ ] Diagrams support text
