---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "register-signing"
    },
    {
      "type": "capability",
      "id": "edit-signing"
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

# Signing money is positive, finite and within the retained legacy bound

Registration/edit requires positive finite money with rounded legacy amount no greater than 2,147,483,647. The precise amount and currency are retained alongside that amount. Trade signing and its supported order money changes share the financial transaction.
