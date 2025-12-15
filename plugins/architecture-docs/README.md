# architecture-docs

Industry-standard documentation: ADRs (MADR format), technical specifications, and RFCs. Follows documentation-as-architecture principles.

## Commands

| Command | Description |
|---------|-------------|
| `/adr <title>` | Create ADR in MADR format with decision drivers and alternatives |
| `/tech-spec <feature>` | Technical specification with quality attributes and operational concerns |
| `/rfc <title>` | Request for Comments for major proposals |

## Agent

**technical-writer** - Senior architect focused on documentation. Creates precise, actionable documents that capture architectural decisions and their rationale.

## Skill

**documentation** - Activates when writing architecture documentation. Brings knowledge of MADR format, quality attribute specifications, and documentation best practices.

## Document Types

### ADR (Architecture Decision Record)
MADR format with:
- Context and problem statement
- Decision drivers
- Considered options with pros/cons
- Decision outcome
- Consequences (positive, negative, risks)

### Technical Specification
Includes:
- Problem statement and goals
- Quality attribute requirements
- Proposed solution with trade-offs
- Operational concerns
- Risks and mitigations

### RFC (Request for Comments)
For major proposals:
- Motivation and background
- Detailed design
- Alternatives considered
- Migration strategy
- Open questions

## Usage

```
/adr use-event-sourcing-for-orders

"We need to decide whether to use event sourcing for the
order aggregate. Key concerns are audit trail and replay."
```

Creates a properly structured MADR with decision drivers, options analysis, and documented consequences.
