---
name: architecture-review
description: Evaluate architecture proposals using quality attribute analysis. Use this skill whenever the user asks for a design review, wants feedback on an architecture, is assessing trade-offs between approaches, or needs a pre-implementation design check -- even if they just say "take a look at this design" or "what do you think about this approach."
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Architecture Review

Provide rigorous, constructive evaluation of architectural proposals.

## Activation Contexts

- Reviewing architecture documents or proposals
- Evaluating technical design decisions
- Assessing trade-offs between approaches
- Pre-implementation design reviews
- Post-incident architectural retrospectives

## Review Approach

### 1. Understand Before Evaluating

Ask these questions before forming opinions -- jumping to critique without context produces generic feedback that wastes everyone's time:

- What problem is being solved?
- What are the constraints (team size, timeline, budget)?
- What quality attributes are prioritized?
- What trade-offs were already considered?

### 2. Evaluate Quality Attributes

Reference `shared/core-knowledge.md` when discussing quality attribute metrics and trade-off pairs.

Key questions per attribute:
- **Performance**: What are the latency/throughput requirements? Where are the hot paths?
- **Scalability**: What needs to scale independently? Where are the bottlenecks?
- **Availability**: What's the target SLA? How are failures handled?
- **Security**: Is there a threat model? How is data protected at rest and in transit?
- **Modifiability**: How easy is it to change? What's the coupling story?
- **Deployability**: Can components deploy independently? Is rollback safe?
- **Observability**: How will you know something is wrong? How will you diagnose it?

### 3. Identify Trade-offs

Every architectural decision trades one quality for another. Surface these explicitly:
- What's gained and what's lost with each decision?
- Are the trade-offs acknowledged in the proposal, or implicit?
- Do the trade-offs fit the context (e.g., trading consistency for availability makes sense for a product catalog, not for a payment ledger)?

When quality attributes conflict, document the tension explicitly: state which attribute wins, why it wins in this context, and suggest fitness functions to monitor the attribute that lost.

### 4. Assess Risks

- **Sensitivity points**: Decisions where a small change produces a disproportionate effect on a quality attribute. For example, choosing sync vs async communication between two services can dramatically shift both latency and availability characteristics.
- **Single points of failure**: Components whose failure takes down the whole system
- **Complexity hotspots**: Areas where multiple concerns intersect and changes become risky

### 5. Suggest Fitness Functions

Fitness functions are automated checks that validate architectural characteristics over time -- they catch architectural drift before it becomes a crisis. Suggest concrete, measurable checks like:
- "No service-to-service call exceeds 200ms at p99"
- "No module has more than 5 outgoing dependencies"
- "Test coverage for domain layer stays above 80%"

Read `references/fitness-functions-examples.md` for a catalog organized by quality attribute.

## Feedback Structure

**Quick review**: Strengths → Concerns → Questions → Suggestions

**Detailed review**: QA analysis → Trade-offs → Risks → Prioritized recommendations

Write review artifacts to `docs/reviews/` following `shared/output-conventions.md`.

## Principles

- **Be specific** -- reference concrete elements, not generalities. "The OrderService has 14 dependencies crossing 3 bounded contexts" beats "there's too much coupling."
- **Be constructive** -- every criticism includes a suggested alternative, because pointing out problems without solutions is venting, not reviewing.
- **Prioritize** -- lead with critical issues. A missing failure handling strategy matters more than a naming inconsistency.
- **Respect context** -- a startup MVP has different quality needs than a banking platform. Evaluate against stated goals, not ideal architecture.
- **Be honest** -- don't soften findings. "This will fail under load" is more useful than "you might want to consider performance implications."

## Common Anti-Patterns to Flag

| Anti-Pattern | Why It Matters | How to Spot It |
|-------------|---------------|----------------|
| Distributed monolith | Worst of both worlds: distributed complexity without independent deployability | Services that must deploy together or share databases |
| Missing failure handling | Systems that only work on the happy path collapse under real conditions | No circuit breakers, no retry policies, no fallback behavior |
| Implicit QA assumptions | Unstated assumptions become unpleasant surprises in production | No explicit SLAs, no capacity planning, "it should be fast enough" |
| Undocumented trade-offs | Future teams re-litigate decisions without context | Decisions made but no ADRs explaining why |
| Over-engineering | Complexity without corresponding benefit wastes effort and creates maintenance burden | Abstractions with one implementation, microservices for a 3-person team |
| Missing observability | Can't fix what you can't see | No structured logging, no distributed tracing, no alerting strategy |
| Tight external coupling | External changes break your system | Direct integration without anti-corruption layers |

Read `references/anti-patterns-guide.md` for detailed detection heuristics and remediation strategies.
