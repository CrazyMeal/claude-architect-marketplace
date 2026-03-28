# Fitness Function Examples

Fitness functions are automated checks that validate architectural characteristics over time. They catch drift before it becomes a crisis.

## By Quality Attribute

### Performance
- No API endpoint exceeds 200ms at p99 latency
- Database query execution time stays under 50ms at p95
- No single request triggers more than N database queries (N+1 detection)
- Memory usage per request stays under threshold

### Scalability
- Services remain stateless (no local file storage, no in-memory session state)
- No single database table exceeds N million rows without partitioning strategy
- Horizontal scaling test: 2x instances handles ~2x throughput

### Availability
- No single point of failure (every critical component has redundancy)
- Mean time to recovery (MTTR) under target threshold
- Health check endpoints respond within 1 second
- Circuit breaker triggers do not cascade across services

### Security
- No secrets in source code or configuration files
- All external APIs require authentication
- Dependency vulnerability scan passes (no critical/high CVEs)
- Data at rest is encrypted for PII-containing stores

### Modifiability
- No module has more than N outgoing dependencies
- No circular dependencies between modules/packages
- Domain layer has zero infrastructure imports
- Test coverage for domain logic stays above threshold

### Deployability
- Build time stays under N minutes
- Deployment requires zero manual steps
- Rollback completes within N minutes
- No service requires coordinated deployment with another service

### Observability
- Every service exposes health and readiness endpoints
- All cross-service calls produce distributed traces
- Structured logging covers all error paths
- Alert coverage exists for every defined SLO

## Implementation Approaches

**Build-time checks:** Static analysis, dependency rules, architecture tests (e.g., ArchUnit, NetArchTest, deptry)

**Deploy-time checks:** Integration tests, contract tests, smoke tests in staging

**Runtime checks:** SLO monitoring, anomaly detection, synthetic transactions

**Periodic checks:** Dependency audits, load tests, chaos engineering experiments
