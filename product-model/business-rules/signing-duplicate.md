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

# Signing duplicate detection and financial write share one checked boundary

The customer, date, rounded amount and currency duplicate check shares the checked write boundary. A duplicate returns comparison information and requires explicit manual confirmation to override. AI acceptance never forces that override.
