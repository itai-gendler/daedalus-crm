---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    }
  ],
  "relations": [
    {
      "entity": "customer",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "lead",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "assigned-contact",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "unassigned-contact",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "opportunity",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "signing",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "order",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "follow-up",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "plan",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "task",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "channel",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "supplier",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "crm-account",
      "verb": "publishes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "audit-log",
      "verb": "publishes",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "ai-access"
}
---

# Mcp Connection

The current book’s enabled/disabled delegated read-only MCP connection, bound to its generating member. Credential rotation invalidates prior access.

## Information kept

- **Enabled** — Whether this MCP token currently accepts incoming requests.
- **Address** — The incoming MCP endpoint address offered with this connection.
- **Credential** — The actual private configured key or current MCP bearer credential, distinct from a disclosed hint.
- **Generating member** — The CRM account that generated this incoming MCP connection.
- **Generation time** — When the current MCP token was generated or rotated.

## States

### Enabled

The retained MCP token accepts requests that pass its actual generator and deployment checks.

### Disabled

This MCP connection does not accept later incoming requests.
