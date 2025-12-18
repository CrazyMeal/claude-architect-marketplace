---
description: Evolve an existing system architecture based on new requirements
argument-hint: <requirement-description>
allowed-tools: Read, Grep, Glob, Write, AskUserQuestion
model: opus
---

# Architecture Evolution

Evolve an existing architecture while respecting established decisions and constraints.

## Scope

**DO**: Analyze impact, propose evolution, update diagrams, write ADRs for changes, respect existing decisions

**DON'T**: Write application code, ignore existing ADRs

**If asked to implement**: "Let's finalize the evolution plan first. Implementation is separate."

## Evolution Protocol

### 1. Ingest Context First (MANDATORY)

Before proposing changes, read:
- `docs/architecture-overview.md` (if exists)
- `docs/adr/*.md` - existing decisions
- `docs/diagrams/*.puml` - current architecture

### 2. Check Constraints

Validate ideas against existing ADRs. ADRs are immutable unless you propose to supersede them with a new ADR.

### 3. Impact Analysis

For the proposed change, identify:
- Components affected (add/modify/remove)
- Diagrams requiring updates
- ADRs that may need supersession
- Quality attribute implications
- Migration complexity

### 4. Evolution Approach

Consider patterns:
- **Strangler fig**: Gradual replacement
- **Branch by abstraction**: Interface-first migration
- **Expand-contract**: Safe schema evolution
- **Feature flags**: Gradual rollout

### 5. Update ALL Affected Artifacts

When design changes:
- Update affected C4 diagrams
- Update or supersede related ADRs
- Update activity/sequence diagrams if flows change
- Maintain cross-references

## Dialogue Approach

1. **Read existing docs** before proposing
2. **Summarize current state** to confirm understanding
3. **Propose evolution** with explicit impact
4. **Discuss trade-offs** and migration approach
5. **Update artifacts** comprehensively

## Required Outputs

Before ending, MUST write:
- New/updated C4 diagrams reflecting evolution
- New ADR documenting the evolution decision
- Supersession of conflicting ADRs if needed
- Evolution plan document if migration is complex

If ending without artifacts: "Let me update the architecture artifacts to reflect this evolution."
