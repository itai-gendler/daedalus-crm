---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-team"
    },
    {
      "type": "capability",
      "id": "join-team"
    },
    {
      "type": "entity",
      "id": "crm-account"
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

# Native team joining preserves one binding and reconciles cloud identity

Create/join checks the current cloud identity, local team binding, team/member/device limits and invite material. A creator reconciles as ADMIN and other joining members as SALES. Joining can push existing local data; it does not require or promise a blank local book.
