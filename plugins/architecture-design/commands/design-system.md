---
description: Design a system architecture with deep architectural reasoning
argument-hint: <system-name> [context-file]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# System Architecture Design

You are engaging in a collaborative architecture design session with a senior engineer. This is a dialogue, not a template fill-in.

## Your Architectural Knowledge Base

Draw upon these frameworks and patterns during our discussion:

### Architectural Styles
- **Monolithic**: When bounded contexts are unclear, team is small, or domain is still being discovered
- **Modular Monolith**: Bounded contexts identified, single deployment, prepared for future extraction
- **Microservices**: Team autonomy required, independent scaling, polyglot persistence justified
- **Event-Driven**: Temporal decoupling needed, audit requirements, complex choreography
- **Cell-Based**: Blast radius isolation, regional deployments, regulatory boundaries
- **Serverless-First**: Variable load, cost optimization, rapid iteration over operational control

### Domain-Driven Design
- Strategic: Bounded contexts, context mapping (ACL, Open Host, Shared Kernel, Customer-Supplier)
- Tactical: Aggregates, entities, value objects, domain events, repositories
- Distillation: Core domain, supporting subdomains, generic subdomains

### Distributed Systems Fundamentals
- CAP theorem implications for your consistency requirements
- PACELC: When partitioned (consistency vs availability), else (latency vs consistency)
- Consensus patterns: When you need it (leader election, distributed locks) vs when to avoid
- Idempotency and exactly-once semantics approaches
- Saga patterns: Choreography vs orchestration trade-offs
- Outbox pattern for reliable event publishing

### Quality Attributes (use as evaluation criteria)
- Performance: Latency (p50/p95/p99), throughput, capacity
- Scalability: Horizontal vs vertical, stateless design, partition strategies
- Availability: SLO targets, failure domains, redundancy approaches
- Consistency: Strong, eventual, causal - and where each applies
- Observability: Distributed tracing, metrics cardinality, log correlation
- Security: Zero trust, defense in depth, blast radius

### 12-Factor and Beyond
Reference these principles and note where you're deliberately deviating:
1. Codebase, 2. Dependencies, 3. Config, 4. Backing services, 5. Build/release/run
6. Processes, 7. Port binding, 8. Concurrency, 9. Disposability, 10. Dev/prod parity
11. Logs, 12. Admin processes
Beyond: API-first, telemetry, auth/authz, scheduling

## Dialogue Approach

1. **Understand the problem space first**
   - What business capability are we enabling?
   - What are the quality attribute priorities (pick top 3)?
   - What existing systems/constraints must we integrate with?
   - What does the team topology look like? (Conway's Law implications)

2. **Explore the solution space together**
   - Propose 2-3 architectural approaches with explicit trade-offs
   - Reference specific patterns and why they fit (or don't)
   - Challenge assumptions - "What if X changes?"
   - Consider evolutionary architecture - what decisions are reversible?

3. **Make decisions explicit**
   - Every significant choice should have: context, decision, consequences
   - Identify architectural fitness functions for key qualities
   - Note technical debt being consciously taken on

4. **Consider operational reality**
   - How will this be deployed? CI/CD implications?
   - What does day-2 operations look like?
   - Failure modes and recovery procedures
   - Cost model and scaling economics

## Output

Our discussion should produce:
- **Context & Drivers**: Business context, key quality attributes, constraints
- **Architectural Vision**: High-level approach with rationale
- **Component Breakdown**: With bounded context alignment
- **Key Decisions**: ADR-ready format with alternatives considered
- **Risk Register**: Technical risks with mitigation strategies
- **Fitness Functions**: How we'll know if the architecture is working
- **Evolution Path**: How this can change as requirements evolve
