---
feature: [feature-name]
component: api
related-diagrams:
  - ../../diagrams/seq-[flow].puml
related-adrs: []
---

# API Design: [Feature Name]

## Overview

[Brief description of API scope and consumers]

## Endpoints

### [Resource Name]

#### Create [Resource]

```
POST /api/v1/[resources]
```

**Request:**
```json
{
  "field": "value"
}
```

**Response:** `201 Created`
```json
{
  "id": "uuid",
  "field": "value",
  "createdAt": "ISO8601"
}
```

**Errors:**
| Status | Code | Description |
|--------|------|-------------|
| 400 | INVALID_INPUT | [reason] |
| 409 | CONFLICT | [reason] |

#### Get [Resource]

```
GET /api/v1/[resources]/{id}
```

**Response:** `200 OK`
```json
{
  "id": "uuid",
  "field": "value"
}
```

## Authentication

[Auth mechanism, token format, scopes required]

## Rate Limiting

| Endpoint | Limit | Window |
|----------|-------|--------|
| POST /resources | 100 | 1 min |
| GET /resources | 1000 | 1 min |

## Versioning Strategy

[How API versions are handled]

## Related Flows

See: [Sequence Diagram](../../diagrams/seq-[flow].puml)
