---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-signing"
    },
    {
      "type": "entity",
      "id": "order"
    },
    {
      "type": "entity",
      "id": "signing"
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

# Signing deletion restores only eligible prior values

Financial deletion and supported linked order removal share their transaction. Eligible prior opportunity values and the person's selected customer-status restoration can follow. Later changed values and completed work are retained.
