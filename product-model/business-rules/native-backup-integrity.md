---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "backup-local-data"
    },
    {
      "type": "capability",
      "id": "restore-local-data"
    },
    {
      "type": "entity",
      "id": "ai-config"
    },
    {
      "type": "entity",
      "id": "assigned-contact"
    },
    {
      "type": "entity",
      "id": "audit-log"
    },
    {
      "type": "entity",
      "id": "backup"
    },
    {
      "type": "entity",
      "id": "business-config"
    },
    {
      "type": "entity",
      "id": "channel"
    },
    {
      "type": "entity",
      "id": "conversation"
    },
    {
      "type": "entity",
      "id": "crm-account"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "follow-up"
    },
    {
      "type": "entity",
      "id": "import-batch"
    },
    {
      "type": "entity",
      "id": "lead"
    },
    {
      "type": "entity",
      "id": "mcp-connection"
    },
    {
      "type": "entity",
      "id": "opportunity"
    },
    {
      "type": "entity",
      "id": "order"
    },
    {
      "type": "entity",
      "id": "plan"
    },
    {
      "type": "entity",
      "id": "signing"
    },
    {
      "type": "entity",
      "id": "supplier"
    },
    {
      "type": "entity",
      "id": "task"
    },
    {
      "type": "entity",
      "id": "unassigned-contact"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
    }
  ]
}
---

# Restore preserves a consistent copy and validates its selected backup

Backup creates a consistent snapshot. Restore validates allowed names/paths and integrity, preserves the current copy, stops/replaces/restarts the local service and retains its failure boundary. A post-replacement failure may already have changed local data.
