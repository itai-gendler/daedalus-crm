---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-customer"
    },
    {
      "type": "capability",
      "id": "edit-customer"
    },
    {
      "type": "capability",
      "id": "edit-channel"
    },
    {
      "type": "entity",
      "id": "channel"
    },
    {
      "type": "entity",
      "id": "customer"
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

# Customer attribution rejects the checked referral cycles

Customer/source/channel edits apply their visible referral-cycle checks and resolve direct versus inherited attribution. Changing a channel or relationship does not automatically rewrite all descendant customer history or already frozen signing ownership.
