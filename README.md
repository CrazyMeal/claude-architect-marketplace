# Claude Architect Marketplace

A curated marketplace of Claude Code plugins for software architecture design, analysis, documentation, and diagramming.

## Purpose

This marketplace provides tools for experienced software engineers to produce high-quality architectural artifacts before code production:

- **Design** new system architectures with structured thinking
- **Analyze** existing codebases for patterns and issues
- **Generate** diagrams as code (Mermaid, PlantUML, D2)
- **Document** decisions (ADRs), specifications, and RFCs
- **Review** architectural proposals and assess risks

## Installation

### Add to Your Project

Add this marketplace to your project's `.claude/settings.json`:

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

### Install Individual Plugins

```bash
claude plugin install architecture-design@architect
claude plugin install diagrams-as-code@architect
```

## Available Plugins

### architecture-design

Design software architectures from scratch.

**Commands:**
- `/design-system <name>` - Design a new system architecture
- `/design-component <name>` - Design a specific component

**Agent:** `system-architect` - Expert system design assistance

**Skill:** `system-design` - Automatic guidance during architecture discussions

---

### architecture-analysis

Analyze existing codebases and architectures.

**Commands:**
- `/analyze-codebase [dir]` - Full architecture analysis
- `/analyze-dependencies [file]` - Dependency audit

**Agent:** `code-analyst` - Expert codebase analysis

**Skill:** `codebase-analysis` - Automatic insights during code exploration

---

### diagrams-as-code

Generate architecture diagrams in multiple formats.

**Commands:**
- `/diagram <type> <format>` - Generate a diagram
- `/diagram-from-code <type> [dir]` - Generate from codebase
- `/c4-diagram <level>` - Generate C4 model diagrams

**Agent:** `diagram-assistant` - Expert diagram creation

**Skill:** `diagram-generation` - Automatic diagram suggestions

**Supported Formats:**
- Mermaid (default, GitHub-compatible)
- PlantUML (detailed, C4 support)
- D2 (modern, clean)

---

### architecture-docs

Generate architecture documentation.

**Commands:**
- `/adr <title>` - Create an Architecture Decision Record
- `/tech-spec <feature>` - Create a technical specification
- `/rfc <title>` - Create a Request for Comments

**Agent:** `technical-writer` - Expert documentation assistance

**Skill:** `documentation` - Automatic documentation support

**Includes Templates:** ADR, Tech Spec

---

### architecture-review

Review and critique architectural decisions.

**Commands:**
- `/review-architecture [doc]` - Full architecture review
- `/review-adr <file>` - Review an ADR
- `/risk-assessment [doc]` - Assess architectural risks

**Agent:** `architecture-reviewer` - Expert review assistance

**Skill:** `architecture-review` - Automatic feedback on shared designs

## Usage Examples

### Design a New System

```
/design-system payment-service

Or describe what you need:
"I need to design a payment processing system that handles
subscriptions, one-time payments, and refunds."
```

### Analyze an Existing Codebase

```
/analyze-codebase ./src

Or ask naturally:
"What patterns does this codebase use?"
"Are there any architectural issues in this project?"
```

### Generate Diagrams

```
/diagram sequence mermaid
/c4-diagram context
/diagram-from-code module ./src

Or describe what you need:
"Create a sequence diagram showing the checkout flow"
"Generate a C4 container diagram for our system"
```

### Create Documentation

```
/adr use-postgresql-for-persistence
/tech-spec user-authentication
/rfc migrate-to-microservices

Or ask naturally:
"Document our decision to use event sourcing"
"Create a tech spec for the notification system"
```

### Review Architecture

```
/review-architecture ./docs/architecture.md
/risk-assessment ./design/
/review-adr ./docs/adrs/001-database-choice.md

Or share a design:
"What do you think of this architecture? [paste design]"
```

## Token Optimization

This marketplace is designed for token efficiency:

1. **Concise prompts** - Commands produce structured output without verbose explanations
2. **Model selection** - Uses `haiku` for simple tasks, `sonnet` for complex analysis
3. **Focused output** - Templates ensure complete but not excessive documentation
4. **Progressive detail** - Start with summaries, drill down as needed

## Quality Focus

Quality is the primary success criterion:

- **Structured outputs** - Consistent, professional formats
- **Best practices** - Industry-standard patterns and templates
- **Review capability** - Built-in quality checks
- **Complete artifacts** - Production-ready documentation

## Directory Structure

```
claude-architect-marketplace/
├── .claude-plugin/
│   ├── plugin.json           # Marketplace manifest
│   └── marketplace.json      # Plugin catalog
├── plugins/
│   ├── architecture-design/
│   │   ├── .claude-plugin/plugin.json
│   │   ├── commands/
│   │   ├── agents/
│   │   └── skills/
│   ├── architecture-analysis/
│   ├── diagrams-as-code/
│   ├── architecture-docs/
│   └── architecture-review/
└── README.md
```

## Contributing

Contributions welcome. Please:

1. Follow the existing plugin structure
2. Keep prompts concise and focused
3. Include examples in command files
4. Test with various codebases

## License

MIT
