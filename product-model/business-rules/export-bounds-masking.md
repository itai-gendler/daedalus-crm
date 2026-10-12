---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "export-customers"
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

# Export preserves independent customer and communication limits

Filtered export spans pages up to twenty thousand customers and fifty thousand follow-ups, reporting the separate truncation flags. Only exported customers' follow-ups enter the second sheet. Shared-demo masking is retained.
