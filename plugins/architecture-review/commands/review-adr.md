---
description: Review an Architecture Decision Record for completeness and quality
argument-hint: <adr-file>
allowed-tools: Read, Grep, Glob
model: haiku
---

# ADR Review

Quick quality review of an Architecture Decision Record.

## Review Checklist

### Structure (MADR)
- [ ] Status clearly stated
- [ ] Date recorded
- [ ] Decision makers identified
- [ ] Context explains the problem

### Decision Quality
- [ ] Decision drivers are concrete and measurable
- [ ] Multiple options genuinely considered
- [ ] Chosen option justified against drivers
- [ ] Trade-offs explicitly acknowledged

### Consequences
- [ ] Positive consequences linked to drivers
- [ ] Negative consequences honestly stated
- [ ] Risks identified

### Connections
- [ ] Related ADRs linked
- [ ] External references provided
- [ ] Supersedes relationship clear (if applicable)

## Common Issues

| Issue | Problem | Fix |
|-------|---------|-----|
| Vague context | "We need a database" | State specific requirements |
| Fake options | Only one real option | Include genuinely considered alternatives |
| Missing drivers | No criteria for decision | List measurable requirements |
| Hidden trade-offs | Only benefits listed | Be honest about costs |
| Orphan ADR | No links | Connect to related decisions |

## Output Format

```markdown
## ADR Review: [Title]

**Overall**: Pass / Pass with suggestions / Needs revision

### Strengths
- [What's done well]

### Issues
- **[Critical/Minor]**: [Issue and suggestion]

### Suggestions
- [Improvement ideas]
```
