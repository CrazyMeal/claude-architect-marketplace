# Output Conventions

## Mandatory Artifact Production

**Every architecture session MUST produce written artifacts.** Never end having only discussed.

If user tries to end without artifacts: "Let me generate the artifacts first."

## Standard Output Locations

| Artifact Type | Location | Naming |
|---------------|----------|--------|
| C4 Diagrams | `docs/diagrams/` | `c4-[level]-[name].puml` |
| Sequence Diagrams | `docs/diagrams/` | `seq-[flow].puml` |
| Activity Diagrams | `docs/diagrams/` | `activity-[process].puml` |
| Domain Models | `docs/diagrams/` | `domain-[context].puml` |
| ADRs | `docs/adr/` | `NNNN-[title].md` |
| Tech Specs | `docs/specs/` | `spec-[feature].md` |
| RFCs | `docs/rfcs/` | `rfc-NNNN-[title].md` |
| Reviews | `docs/reviews/` | `review-[system]-[date].md` |
| Review Actions | `docs/reviews/actions/[priority]/` | `ACTION-NNN-[title].md` |

## Document Consistency Protocol

### Before Writing
1. Read `docs/` for existing architecture documentation
2. Check `docs/adr/` for decisions that may affect your work
3. Check `docs/diagrams/` to understand current state

### When Updating
- Design changes existing decision → New ADR that supersedes
- Design changes system boundaries → Update ALL affected C4 diagrams
- Design adds/removes components → Update Container diagram AND related docs

### Consistency Checks
- New decisions don't contradict existing ADRs
- Diagrams reflect current design state
- Component names consistent across all documents
- Technology choices match between ADRs and diagrams

**If you find inconsistencies, fix them proactively or flag them explicitly.**

## Review Action File Format

```markdown
# ACTION-NNN: [Title]

## Priority
Critical | Important | Consider

## Finding
[What was identified]

## Impact
[Why this matters - quality attributes affected]

## Recommendation
[Specific action to take]

## Acceptance Criteria
- [ ] [Measurable outcome 1]
- [ ] [Measurable outcome 2]

## Related
- Review: [link to main review]
- Affected components: [list]
```
