---
description: Perform a risk assessment on an architecture or design
argument-hint: [document-or-directory]
allowed-tools: Read, Grep, Glob
model: sonnet
---

# Architecture Risk Assessment

Identify and assess risks in an architecture.

## Risk Categories

1. **Technical**: Technology choices, complexity, dependencies
2. **Operational**: Deployment, monitoring, maintenance
3. **Security**: Vulnerabilities, data protection
4. **Performance**: Scalability, latency, throughput
5. **Organizational**: Skills, ownership, coordination

## Risk Assessment Process

1. **Identify**: Find potential risks
2. **Analyze**: Determine likelihood and impact
3. **Prioritize**: Rank by severity
4. **Mitigate**: Suggest countermeasures

## Output Format

```
## Risk Assessment: [System/Design Name]

### Risk Summary
| Risk | Category | Likelihood | Impact | Severity |
|------|----------|------------|--------|----------|
| [R1] | [cat]    | H/M/L      | H/M/L  | Critical/High/Medium/Low |

### Detailed Analysis

#### [R1]: [Risk Name]
- **Category:** [Technical/Operational/Security/Performance/Organizational]
- **Description:** [What could go wrong]
- **Likelihood:** [High/Medium/Low] - [Why]
- **Impact:** [High/Medium/Low] - [What happens if it occurs]
- **Severity:** [Likelihood × Impact]
- **Mitigations:**
  1. [Mitigation strategy]
  2. [Mitigation strategy]
- **Residual Risk:** [After mitigations]

### Top 3 Risks to Address
1. [R#]: [One-line summary] - [Recommended action]
2. [R#]: [One-line summary] - [Recommended action]
3. [R#]: [One-line summary] - [Recommended action]

### Monitoring Recommendations
- [What to watch for]
```

## Guidelines

- Focus on significant risks, not all possibilities
- Be specific about likelihood rationale
- Mitigations should be actionable
- Consider both short and long-term risks
