---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-customer"
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

# Conflicting customer fields are not overwritten by whole-record merge

The whole-record edit path merges nonoverlapping field changes with bounded retries. An overlapping change produces a conflict instead of replacing the later values. Inline edits and auxiliary profile paths retain their different established guards.
