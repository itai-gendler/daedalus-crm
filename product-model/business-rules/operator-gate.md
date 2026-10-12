---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "enter-ops"
    },
    {
      "type": "capability",
      "id": "browse-ops-overview"
    },
    {
      "type": "entity",
      "id": "cloud-account"
    },
    {
      "type": "entity",
      "id": "service-config"
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

# Operations entry uses its hosted token or configured active identity

Product operations accepts the hosted console token or its configured active operations identity. Native entry exchange uses a one-use code valid for sixty seconds and establishes a twelve-hour console session. CRM ADMIN alone does not identify a product operator.
