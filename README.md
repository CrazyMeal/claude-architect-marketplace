# Claude Architect Marketplace

Expert-level architecture plugins for Claude Code. Built for senior engineers who need sophisticated architectural dialogue, not templated outputs.

## Philosophy

These plugins enable **peer-level architectural conversations**. They bring deep knowledge of:

- **Domain-Driven Design**: Bounded contexts, aggregates, context mapping, anti-corruption layers
- **Distributed Systems**: CAP/PACELC, saga patterns, event sourcing, CQRS, outbox pattern
- **Cloud-Native**: 12-factor apps, container patterns, service mesh, observability
- **Architecture Evaluation**: ATAM-style quality attribute analysis, trade-off identification, fitness functions
- **Industry Standards**: C4 model, ADRs (MADR format), technical specifications

All plugins use **Claude Opus** for the deepest architectural reasoning.

## Installation

Add to your project's `.claude/settings.json`:

```json
{
  "extraKnownMarketplaces": {
    "architect": {
      "source": {
        "type": "github",
        "repo": "CrazyMeal/claude-architect-marketplace"
      }
    }
  },
  "enabledPlugins": [
    "architecture-design@architect",
    "architecture-analysis@architect",
    "diagrams-as-code@architect",
    "architecture-docs@architect",
    "architecture-review@architect"
  ]
}
```

## Plugins

### architecture-design

Collaborative system design drawing on DDD, distributed systems theory, and evolutionary architecture.

**Commands:**
- `/cam-design-system <name>` - Full system architecture with bounded contexts, quality attributes
- `/cam-design-component <name>` - Component design with DDD tactical patterns, integration strategies

**Agent:** `system-architect` - Principal architect for design discussions

**Knowledge includes:**
- Architectural styles (microservices, event-driven, cell-based, modular monolith)
- DDD strategic and tactical patterns
- CAP/PACELC implications
- Saga patterns (orchestration vs choreography)
- 12-factor and beyond-12-factor principles
- Conway's Law and team topology considerations

---

### architecture-analysis

Deep codebase analysis with pattern recognition and technical debt assessment.

**Commands:**
- `/cam-analyze-codebase [dir]` - Structural analysis, domain model assessment, coupling metrics
- `/cam-analyze-dependencies [file]` - Architectural dependency analysis (not just version checking)

**Agent:** `code-analyst` - Principal engineer for reverse-engineering existing systems

**Capabilities:**
- Coupling analysis (afferent/efferent, instability)
- Pattern and anti-pattern detection
- Technical debt categorization (reckless/prudent, deliberate/inadvertent)
- Bounded context identification from code
- Evolution readiness assessment

---

### diagrams-as-code

C4 model diagrams with proper abstraction discipline.

**Commands:**
- `/cam-diagram <type> [format]` - Architecture diagrams with purpose-driven selection
- `/cam-c4-diagram <level>` - C4 diagrams: Context, Container, Component, plus Deployment and Dynamic
- `/cam-diagram-from-code <type> [dir]` - Generate diagrams from existing code

**Agent:** `diagram-assistant` - Architecture visualization expert

**C4 Knowledge:**
- Abstraction levels and when to use each
- Notation standards (PlantUML C4 library, Mermaid)
- Supplementary diagrams (deployment, dynamic)
- Structurizr DSL for architecture-as-code

**Formats:** PlantUML (recommended for C4), Mermaid (docs), D2 (presentations)

---

### architecture-docs

Industry-standard documentation following best practices.

**Commands:**
- `/cam-adr <title>` - MADR format with decision drivers, alternatives, consequences
- `/cam-tech-spec <feature>` - Specification with quality attributes, operational concerns, risks
- `/cam-rfc <title>` - Request for Comments for major proposals

**Agent:** `technical-writer` - Senior architect focused on documentation

**Documentation Knowledge:**
- MADR (Markdown Any Decision Record) format
- Y-statement format for decisions
- Quality attribute specifications
- C4 documentation practices
- Runbook structure

---

### architecture-review

Rigorous evaluation using quality attribute analysis.

**Commands:**
- `/cam-review-architecture [doc]` - ATAM-inspired review with quality scenarios
- `/cam-risk-assessment [doc]` - Comprehensive risk taxonomy and mitigation strategies
- `/cam-review-adr <file>` - ADR quality review

**Agent:** `architecture-reviewer` - Principal architect for design evaluation

**Evaluation Framework:**
- Quality attribute scenarios (stimulus → response under conditions)
- Sensitivity points and trade-off points
- Risk categorization (technical, operational, organizational, external)
- Fitness function recommendations

## Usage Examples

### Designing with Context

```
"I need to design an order processing system. We're expecting
10K orders/day, need to integrate with three payment providers,
and the team has strong Go experience but limited Kafka knowledge."

> The system-architect will ask about quality priorities,
> explore bounded contexts, discuss event-driven vs synchronous
> approaches, and consider your team constraints.
```

### Analyzing for Migration

```
"Analyze this codebase. We're considering extracting the billing
domain into a separate service."

> The code-analyst will identify bounded context boundaries,
> assess coupling, find strangler fig seams, and evaluate
> extraction readiness.
```

### C4 Documentation

```
"/cam-c4-diagram container"

> Generates a proper C4 Container diagram with technology
> annotations, relationship labels, and PlantUML C4 library syntax.
```

### MADR-Format ADRs

```
"/cam-adr use-event-sourcing-for-orders"

> Creates an ADR with decision drivers, considered options with
> pros/cons, decision outcome, and consequences - following
> MADR best practices.
```

### ATAM-Style Review

```
"/cam-review-architecture ./docs/design.md"

> Conducts quality attribute analysis, identifies trade-offs
> and sensitivity points, assesses risks, and provides
> prioritized recommendations.
```

## Quality Focus

These plugins prioritize quality over quantity:

- **Deep knowledge** embedded in prompts, not generic instructions
- **Opus model** for sophisticated reasoning
- **Industry standards** (C4, MADR, ATAM) properly applied
- **Peer-level dialogue** rather than tutorial-style output
- **Evidence-based** recommendations with specific references

## Structure

```
claude-architect-marketplace/
├── .claude-plugin/
│   ├── plugin.json
│   └── marketplace.json
├── plugins/
│   ├── architecture-design/
│   │   ├── commands/     (cam-design-system, cam-design-component)
│   │   ├── agents/       (system-architect)
│   │   └── skills/       (system-design)
│   ├── architecture-analysis/
│   ├── diagrams-as-code/
│   ├── architecture-docs/
│   └── architecture-review/
└── README.md
```

## License

MIT
