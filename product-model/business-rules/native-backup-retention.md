---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "backup-local-data"
    },
    {
      "type": "capability",
      "id": "browse-local-data"
    },
    {
      "type": "entity",
      "id": "backup"
    },
    {
      "type": "entity",
      "id": "cloud-account"
    },
    {
      "type": "entity",
      "id": "desktop-config"
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

# Automatic backup retains its bounded meaningful-data copies

The implemented retention keeps seven meaningful-data daily copies, three upgrade copies and three pre-restore copies. Automatic backup failure does not block application startup.
