---
rfc: [rfc-number]
component: migration
related-diagrams:
  - ../../diagrams/c4-deployment-[env].puml
related-adrs: []
---

# Migration Path: RFC-[NUMBER]

## Current State

[Description of current architecture/system state]

## Target State

[Description of desired end state]

## Migration Strategy

[Overall approach: big bang, strangler fig, parallel run, etc.]

## Phases

### Phase 1: [Name]

**Goal:** [What this phase achieves]

**Duration:** [Estimated effort]

**Tasks:**
- [ ] [Task 1]
- [ ] [Task 2]

**Rollback:** [How to rollback this phase]

**Success Criteria:**
- [ ] [Criterion 1]

### Phase 2: [Name]

**Goal:** [What this phase achieves]

**Duration:** [Estimated effort]

**Tasks:**
- [ ] [Task 1]
- [ ] [Task 2]

**Rollback:** [How to rollback this phase]

**Success Criteria:**
- [ ] [Criterion 1]

## Feature Flags

| Flag | Purpose | Phase | Default |
|------|---------|-------|---------|
| [flag] | [purpose] | [phase] | false |

## Data Migration

### Steps

1. [Step 1]
2. [Step 2]

### Validation

[How to verify data integrity]

### Rollback

[How to reverse data migration]

## Deployment Strategy

See: [Deployment Diagram](../../diagrams/c4-deployment-[env].puml)

[Blue-green, canary, rolling - describe approach]

## Communication Plan

| Audience | Message | Timing |
|----------|---------|--------|
| [audience] | [message] | [when] |

## Risks

| Risk | Mitigation |
|------|------------|
| [risk] | [mitigation] |
