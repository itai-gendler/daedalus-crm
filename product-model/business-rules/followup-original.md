---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "record-followup"
    },
    {
      "type": "capability",
      "id": "restore-followup"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "follow-up"
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

# Original communication text is bounded and not replaced by ordinary edit

Recording/restoration retains the supported original text up to five thousand characters. Ordinary communication editing does not replace that original text.
