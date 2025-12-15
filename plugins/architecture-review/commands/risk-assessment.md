---
description: Comprehensive architectural risk assessment with mitigation strategies
argument-hint: [document-or-directory]
allowed-tools: Read, Grep, Glob
model: opus
---

# Architecture Risk Assessment

Systematic identification and analysis of architectural risks.

## Risk Taxonomy

### Technical Risks

**Complexity Risks**
- Distributed system complexity (network partitions, consistency)
- Integration complexity (multiple systems, protocols)
- State management complexity (distributed state, caching)

**Technology Risks**
- Immature technology (limited production experience)
- Technology lock-in (vendor, framework, cloud)
- Skill gap (team unfamiliar with key technologies)
- Deprecated dependencies (end-of-life components)

**Performance Risks**
- Scaling bottlenecks (single points of contention)
- Latency amplification (deep call chains)
- Resource exhaustion (memory, connections, file handles)

**Data Risks**
- Data consistency (distributed transactions, eventual consistency)
- Data loss (inadequate backup, replication lag)
- Data corruption (race conditions, partial writes)

### Operational Risks

**Deployment Risks**
- Deployment coupling (all-or-nothing deployments)
- Rollback difficulty (stateful changes, schema migrations)
- Environment parity (dev/staging/prod differences)

**Observability Risks**
- Debugging difficulty (distributed tracing gaps)
- Alert fatigue (noisy alerting)
- Blind spots (unmonitored components)

**Recovery Risks**
- MTTR (mean time to recovery)
- Disaster recovery (regional failover capability)
- Data recovery (backup/restore procedures)

### Organizational Risks

**Team Risks**
- Knowledge silos (single points of knowledge failure)
- Conway's Law misalignment (architecture vs org structure)
- Cross-team dependencies (coordination overhead)

**Process Risks**
- Change management (how changes are coordinated)
- Incident response (on-call, escalation procedures)
- Documentation debt (tribal knowledge)

### External Risks

**Dependency Risks**
- Third-party service outages
- API deprecation (external APIs changing)
- Vendor viability (vendor going out of business)

**Compliance Risks**
- Regulatory requirements (GDPR, HIPAA, SOC2)
- Data residency (geographic constraints)
- Audit requirements (logging, access controls)

## Assessment Process

### 1. Risk Identification
For each component and interaction:
- What can fail?
- What are the failure modes?
- What are the blast radius implications?

### 2. Likelihood Assessment

| Level | Criteria |
|-------|----------|
| High | Expected to occur (>50% in next year) |
| Medium | Possible (10-50% in next year) |
| Low | Unlikely (<10% in next year) |

### 3. Impact Assessment

| Level | Criteria |
|-------|----------|
| High | Service unavailable, data loss, security breach |
| Medium | Degraded service, partial functionality loss |
| Low | Minor inconvenience, workaround available |

### 4. Severity Matrix

| | Low Impact | Medium Impact | High Impact |
|---|------------|---------------|-------------|
| **High Likelihood** | Medium | High | Critical |
| **Medium Likelihood** | Low | Medium | High |
| **Low Likelihood** | Low | Low | Medium |

### 5. Mitigation Strategies

For each significant risk:
- **Avoid**: Eliminate the risk source
- **Mitigate**: Reduce likelihood or impact
- **Transfer**: Shift risk (insurance, SLAs)
- **Accept**: Acknowledge and monitor

## Output Format

```markdown
## Risk Assessment: [System Name]

### Assessment Context
- **Scope**: [What was assessed]
- **Date**: [Assessment date]
- **Assessors**: [Who conducted]

### Risk Summary

| ID | Risk | Category | L | I | Severity | Status |
|----|------|----------|---|---|----------|--------|
| R1 | [Risk] | [Cat] | H/M/L | H/M/L | [Sev] | [Open/Mitigated/Accepted] |

### Critical Risks (Immediate Action Required)

#### R[X]: [Risk Name]
- **Category**: [Technical/Operational/Organizational/External]
- **Description**: [Detailed description of the risk]
- **Trigger**: [What causes this risk to manifest]
- **Impact**: [What happens if it occurs]
- **Likelihood Rationale**: [Why this likelihood rating]
- **Current Mitigations**: [What's already in place]
- **Recommended Mitigations**:
  1. [Mitigation 1] - Reduces [likelihood/impact]
  2. [Mitigation 2]
- **Residual Risk**: [After mitigations]
- **Owner**: [Who should address]
- **Timeline**: [When to address]

### High Risks (Address Soon)
[Same structure, briefer]

### Medium/Low Risks
[Summary table only]

### Risk Monitoring

| Risk | Indicator | Threshold | Response |
|------|-----------|-----------|----------|
| [Risk] | [What to monitor] | [When to alert] | [What to do] |

### Recommendations Summary
1. [Prioritized recommendation]
2. [Prioritized recommendation]

### Assumptions and Limitations
- [What this assessment assumed]
- [What was not assessed]
```

## Guidelines

- Focus on architectural risks, not project risks
- Be specific about triggers and impacts
- Mitigations should be actionable
- Consider cascading failures
- Assess residual risk after mitigations
- Assign ownership for follow-up
