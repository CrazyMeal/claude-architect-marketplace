---
feature: [feature-name]
component: operations
related-diagrams:
  - ../../diagrams/c4-deployment-[env].puml
related-adrs: []
---

# Operations: [Feature Name]

## Deployment

See: [Deployment Diagram](../../diagrams/c4-deployment-[env].puml)

### Requirements

| Resource | Specification | Scaling |
|----------|--------------|---------|
| CPU | [cores] | [policy] |
| Memory | [GB] | [policy] |
| Storage | [GB] | [policy] |

### Deployment Strategy
[Blue-green, canary, rolling - describe approach]

## Monitoring

### Key Metrics

| Metric | Description | Alert Threshold |
|--------|-------------|-----------------|
| [metric_name] | [what it measures] | [threshold] |

### SLIs/SLOs

| SLI | Target | Measurement |
|-----|--------|-------------|
| Availability | [target]% | [how measured] |
| Latency p99 | [target]ms | [how measured] |
| Error rate | <[target]% | [how measured] |

### Dashboards
- [Dashboard name and purpose]

### Alerts

| Alert | Condition | Severity | Runbook |
|-------|-----------|----------|---------|
| [name] | [condition] | P1/P2/P3 | [link] |

## Failure Modes

| Failure | Impact | Detection | Recovery |
|---------|--------|-----------|----------|
| [failure scenario] | [what breaks] | [how detected] | [recovery steps] |

### Circuit Breakers

| Dependency | Threshold | Fallback |
|------------|-----------|----------|
| [service] | [threshold] | [fallback behavior] |

## Runbooks

### [Scenario Name]

**Symptoms:** [How to identify this issue]

**Steps:**
1. [Step 1]
2. [Step 2]

**Escalation:** [When and how to escalate]
