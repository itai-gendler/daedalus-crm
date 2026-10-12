---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-customers"
    },
    {
      "type": "entity",
      "id": "assigned-contact"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "lead"
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

# Customer deletion preserves detached contacts and reopens its direct lead

Surviving referral/attribution dependencies can block deletion. Eligible deletion preserves contacts as unassigned and reopens the directly associated lead. Missing/concurrent targets and batch failures retain actual counts and partial results rather than promising universal batch rollback.
