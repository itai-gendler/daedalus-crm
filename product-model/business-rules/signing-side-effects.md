---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "register-signing"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "order"
    },
    {
      "type": "entity",
      "id": "signing"
    },
    {
      "type": "entity",
      "id": "supplier"
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

# New signings freeze owners and edits do not replay closure

New registration retains the then-current sales/channel owners. The person selects eligible linked opportunities, unfinished plans and tasks to close. Editing a signing does not replay that closure. Customer-status work can fail after the financial transaction commits.
