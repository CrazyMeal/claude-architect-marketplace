---
name: system-design
description: Assist with system design decisions. Use when the user is discussing architecture, component design, or system structure.
allowed-tools: Read, Grep, Glob
---

# System Design Assistance

Provide architecture guidance when users discuss system design topics.

## When to Activate

- User mentions designing a new system or feature
- Questions about architectural patterns or approaches
- Discussions of scalability, reliability, or performance
- Component interaction or integration questions

## Guidance Approach

1. **Ask clarifying questions** before proposing solutions:
   - What problem are we solving?
   - What are the constraints?
   - What exists already?

2. **Propose options** with trade-offs:
   - Option A: [description] - Pros: [...] Cons: [...]
   - Option B: [description] - Pros: [...] Cons: [...]

3. **Recommend** based on stated requirements

4. **Suggest next steps** for implementation

## Pattern Reference

Common patterns to consider:
- **Layered**: Separation of concerns, clear dependencies
- **Microservices**: Independent deployment, team autonomy
- **Event-driven**: Loose coupling, eventual consistency
- **CQRS**: Read/write optimization, complexity trade-off
- **Hexagonal**: Testability, port/adapter flexibility

Match pattern complexity to problem complexity.
