---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "favorite-customer"
    },
    {
      "type": "capability",
      "id": "unfavorite-customer"
    },
    {
      "type": "entity",
      "id": "crm-account"
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

# Each CRM account keeps at most eight customer favorites

Favorites belong to the personal CRM account. Adding a ninth favorite evicts the earliest retained favorite and keeps the newest eight.
