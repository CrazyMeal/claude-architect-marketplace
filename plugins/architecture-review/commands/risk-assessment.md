---
description: Comprehensive architectural risk assessment with mitigation strategies
argument-hint: [document-or-directory]
allowed-tools: Read, Grep, Glob, Write
model: opus
---

# Risk Assessment

Systematic identification and assessment of architectural risks.

## Risk Taxonomy

### Technical Risks
- Scalability limits
- Performance bottlenecks
- Single points of failure
- Data consistency issues
- Integration fragility

### Operational Risks
- Deployment complexity
- Monitoring gaps
- Incident response readiness
- Configuration drift
- Disaster recovery gaps

### Organizational Risks
- Team skill gaps
- Knowledge silos
- Conway's Law misalignment
- Vendor dependencies
- Budget constraints

### External Risks
- Third-party API stability
- Compliance requirements
- Security threats
- Market/technology shifts

## Assessment Framework

For each identified risk:

| Factor | Scale | Description |
|--------|-------|-------------|
| Likelihood | 1-5 | Probability of occurrence |
| Impact | 1-5 | Severity if occurs |
| Detectability | 1-5 | How easily detected early |
| Risk Score | L×I | Priority ranking |

## Mitigation Strategies

| Strategy | When to Use |
|----------|-------------|
| Avoid | Change design to eliminate risk |
| Mitigate | Reduce likelihood or impact |
| Transfer | Insurance, SLAs, contracts |
| Accept | Low priority, document decision |

## Required Output

Write to `docs/reviews/risks-[system].md`:

```markdown
# Risk Assessment: [System]

## Executive Summary
- Total risks identified: [N]
- Critical: [N] | High: [N] | Medium: [N] | Low: [N]

## Critical Risks
### RISK-001: [Title]
- **Category**: Technical/Operational/Organizational/External
- **Description**: [What could go wrong]
- **Likelihood**: [1-5] | **Impact**: [1-5] | **Score**: [L×I]
- **Current Controls**: [Existing mitigations]
- **Recommended Mitigation**: [Actions]
- **Owner**: [TBD]
- **Target Date**: [TBD]

## Risk Matrix
| Risk | L | I | Score | Status |
|------|---|---|-------|--------|

## Monitoring Recommendations
[How to track risk indicators]
```
