# Anti-Pattern Detection Guide

Detailed heuristics for identifying and remediating common architectural anti-patterns.

## Distributed Monolith

**What it is:** Services that are deployed independently but cannot function independently -- they share databases, require coordinated deployments, or have synchronous call chains that make them a monolith with network hops.

**Detection signals:**
- Shared database schemas across services
- Deployment order matters ("deploy service A before service B")
- One service failure cascades to multiple others
- Cross-service transactions or distributed locks
- Shared libraries containing business logic (not just utilities)

**Remediation:** Identify true bounded contexts. Each service owns its data. Use async events for cross-boundary communication. Accept eventual consistency where appropriate.

---

## Missing Failure Handling

**What it is:** Systems designed only for the happy path, with no strategy for partial failures, timeouts, or degraded operation.

**Detection signals:**
- No circuit breaker patterns on external calls
- No retry policies (or naive retry-forever loops)
- No timeout configuration on HTTP/RPC calls
- No graceful degradation strategy (e.g., serve cached data when upstream is down)
- Error handling limited to logging and re-throwing

**Remediation:** Map failure modes for each external dependency. Implement circuit breakers with fallback behavior. Define timeout budgets. Design for graceful degradation -- what can the system still do when a dependency is unavailable?

---

## Implicit Quality Attribute Assumptions

**What it is:** Quality requirements that exist only in people's heads, never stated, measured, or validated.

**Detection signals:**
- No explicit SLAs or SLOs
- "It should be fast enough" or "we'll scale when we need to"
- No load testing or capacity planning
- Performance/availability requirements not in the spec
- No fitness functions or architectural tests

**Remediation:** Make every quality assumption explicit and measurable. Define SLOs. Create fitness functions that validate assumptions continuously.

---

## Undocumented Trade-offs

**What it is:** Architectural decisions made without recording the context, alternatives considered, or consequences accepted.

**Detection signals:**
- No ADRs or decision log
- "I think we chose X because..." (tribal knowledge)
- New team members re-litigate settled decisions
- Contradictory patterns in the codebase (different teams chose differently)

**Remediation:** Create ADRs for significant decisions. Record the context and constraints at the time of the decision -- future teams need to know whether the constraints still apply.

---

## Over-Engineering

**What it is:** Complexity that exceeds the problem's requirements, creating maintenance burden without corresponding benefit.

**Detection signals:**
- Abstractions with exactly one implementation
- Microservices architecture for a small team (< 5 engineers)
- Generic frameworks built for hypothetical future requirements
- Configuration-driven behavior that's only configured one way
- Multiple layers of indirection with no clear purpose

**Remediation:** Apply YAGNI. Remove abstractions that don't earn their complexity. Prefer a modular monolith over microservices until team size or scaling demands justify the distributed overhead.

---

## Missing Observability

**What it is:** Systems where problems are discovered by users, not by monitoring, because there's no instrumentation to detect or diagnose issues.

**Detection signals:**
- No structured logging (or only unstructured log.info statements)
- No distributed tracing across service boundaries
- No alerting strategy or SLO-based alerts
- No dashboards for key business and system metrics
- Debugging requires SSH-ing into production machines

**Remediation:** Implement the three pillars: metrics (system and business), logs (structured, correlated), traces (distributed, sampled). Define SLIs and SLOs. Alert on SLO burn rate, not on individual errors.

---

## Tight External Coupling

**What it is:** Direct integration with external systems where changes in the external system's API, data format, or behavior directly break your system.

**Detection signals:**
- External API DTOs used directly in domain logic
- No anti-corruption layer or adapter pattern
- External system's terminology used in your domain model
- A change in a third-party API requires changes across multiple services
- No contract tests against external APIs

**Remediation:** Introduce an anti-corruption layer that translates external concepts to your domain model. Use contract tests to detect external changes early. Isolate external dependencies behind interfaces.

---

## God Service / Big Ball of Mud

**What it is:** A service or module that has accumulated so many responsibilities that it's involved in nearly every operation and is impossible to modify safely.

**Detection signals:**
- One service handles > 30% of all requests
- The service has > 20 database tables
- Most PRs touch this service
- Deployment of this service is high-risk and requires extended testing
- The service name is generic ("main-service", "core", "platform")

**Remediation:** Identify cohesive subdomains within the service. Extract them one at a time using the strangler fig pattern. Start with the subdomain that changes most frequently.
