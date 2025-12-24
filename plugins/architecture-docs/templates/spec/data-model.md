---
feature: [feature-name]
component: data
related-diagrams:
  - ../../diagrams/er-[context].puml
  - ../../diagrams/domain-[context].puml
related-adrs: []
---

# Data Model: [Feature Name]

## Overview

[Brief description of data domain and storage strategy]

## Entity Relationship

See: [ER Diagram](../../diagrams/er-[context].puml)

## Entities

### [Entity Name]

**Table:** `[table_name]`

| Column | Type | Constraints | Description |
|--------|------|-------------|-------------|
| id | UUID | PK | Unique identifier |
| [field] | [type] | [constraints] | [description] |
| created_at | TIMESTAMP | NOT NULL | Creation timestamp |
| updated_at | TIMESTAMP | NOT NULL | Last update timestamp |

**Indexes:**
- `idx_[table]_[column]` on `[column]` - [purpose]

**Relationships:**
- Has many `[related_entity]` via `[foreign_key]`

## Domain Model

See: [Domain Model](../../diagrams/domain-[context].puml)

### Aggregates

| Aggregate | Root Entity | Invariants |
|-----------|-------------|------------|
| [Name] | [Entity] | [Business rules enforced] |

### Value Objects

| Value Object | Properties | Validation |
|--------------|------------|------------|
| [Name] | [fields] | [rules] |

## Data Access Patterns

| Operation | Query Pattern | Expected Load |
|-----------|--------------|---------------|
| [operation] | [pattern] | [requests/sec] |

## Migration Strategy

[How to migrate from current state, if applicable]
