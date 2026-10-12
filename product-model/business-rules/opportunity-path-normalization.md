---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-opportunity"
    },
    {
      "type": "capability",
      "id": "edit-opportunity"
    },
    {
      "type": "capability",
      "id": "advance-opportunity"
    },
    {
      "type": "capability",
      "id": "mark-won"
    },
    {
      "type": "capability",
      "id": "mark-lost"
    },
    {
      "type": "capability",
      "id": "reopen-opportunity"
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

# Opportunity probability normalization follows the invoked path

Guarded save/status paths normalize stage and probability according to their rules. Direct stage movement retains its own normalization, and a path can leave OPEN status with the winning stage. Status, stage and probability are separate kept facts.
