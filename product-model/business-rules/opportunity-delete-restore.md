---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-opportunities"
    },
    {
      "type": "capability",
      "id": "restore-opportunity"
    },
    {
      "type": "entity",
      "id": "opportunity"
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

# Opportunity deletion leaves independent orders and communications intact

Deleting an opportunity does not delete independent orders or communication. Snapshot restoration repairs surviving still-null follow-up links while preserving current independent order state; it does not restore the disabled full quotation/order workflow.
