---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "record-followup"
    },
    {
      "type": "capability",
      "id": "edit-followup"
    },
    {
      "type": "capability",
      "id": "delete-followup"
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

# Communication writes maintain only their heuristic matching work

The supported TASK/REMIND communication paths maintain matching task work using their actual title/date/owner heuristics. They do not establish a durable one-to-one task identity for every communication. Customer latest follow-up is derived from occurred time and recalculated after the applicable writes.
