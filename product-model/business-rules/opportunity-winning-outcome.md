---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "mark-won"
    },
    {
      "type": "capability",
      "id": "advance-opportunity"
    },
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
      "id": "opportunity"
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

# Winning outcomes retain their General and Trade differences

General work can mark an opportunity WON without registering a signing, and a later cancellation or signing failure can leave that win in place. Trade cancellation does not convert the opportunity. Successful registration wins the selected eligible linked opportunity under that path's checks.
