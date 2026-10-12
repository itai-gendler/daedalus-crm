---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "undo-import"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "import-batch"
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

# Each import batch is undone once against its retained snapshots

Undo uses the retained creation/fill snapshots and marks the batch undone. Later changes or dependencies cause retention and partial counts. Auxiliary Trade fingerprints do not fully establish later-change detection for every undo branch.
