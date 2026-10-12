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
      "id": "convert-lead"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "lead"
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

# Customer identity follows its General or Trade normalization

General customer identity uses the supported normalized phone. Trade can use normalized email through its established priority. Duplicate checking follows the corresponding identity path. Shared-demo masked round-trips preserve the original values instead of saving the displayed mask as identity.
