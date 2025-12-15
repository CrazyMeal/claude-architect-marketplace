# architecture-review

Rigorous architecture evaluation using ATAM-inspired quality attribute analysis. Identifies trade-offs, sensitivity points, and risks.

## Commands

| Command | Description |
|---------|-------------|
| `/review-architecture [doc]` | ATAM-inspired review with quality scenarios |
| `/risk-assessment [doc]` | Comprehensive risk taxonomy and mitigation strategies |
| `/review-adr <file>` | ADR quality review |

## Agent

**architecture-reviewer** - Principal architect for design evaluation. Uses formal methods adapted for practical review, focusing on quality attributes and trade-offs.

## Skill

**architecture-review** - Activates when evaluating architectures. Brings systematic approaches to quality attribute analysis and risk identification.

## Review Framework (ATAM-Inspired)

### Quality Attribute Analysis
For each priority attribute:
1. **Scenarios**: Stimulus → Response under conditions
2. **Architectural Support**: How the design addresses it
3. **Risks**: What could cause failure
4. **Sensitivity**: Which decisions affect it most

### Quality Attributes Assessed
- Performance, Scalability, Availability
- Security, Modifiability, Testability
- Deployability, Cost Efficiency, Operational Excellence

### Trade-off Identification
- Sensitivity points (small changes, large impact)
- Trade-off points (multiple QAs in tension)
- Risk points (likely problem areas)

### Modern Concerns
- FinOps / cost-aware architecture
- Cloud-native maturity (12-factor)
- API-first assessment
- Operational excellence

## Usage

```
/review-architecture ./docs/design.md

"Review this design focusing on scalability and cost
efficiency. We're targeting 100K requests/minute."
```

Produces a structured review with quality scenarios, trade-off analysis, identified risks, and prioritized recommendations.
