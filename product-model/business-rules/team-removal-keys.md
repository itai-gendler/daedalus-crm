---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "remove-team-member"
    },
    {
      "type": "capability",
      "id": "rotate-team-invite"
    },
    {
      "type": "entity",
      "id": "sync-membership"
    },
    {
      "type": "entity",
      "id": "sync-team"
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

# Member removal and key redistribution retain their separate failure boundaries

Removal/rotation validates its creator and machine authority. Membership departure and key/envelope stages can fail separately, including departure before complete redistribution. Rotation cannot reclaim previously copied local data.
