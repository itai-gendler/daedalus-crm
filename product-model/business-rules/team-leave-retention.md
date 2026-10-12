---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "leave-team"
    },
    {
      "type": "entity",
      "id": "sync-membership"
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

# A creator cannot leave while other members remain

Leaving retains its membership left time and handles local data according to the established identity. A creator with other members receives a refusal. Offline or already removed membership can still permit a local exit. The known noncreator pruning path keeps its scoped work; an unknown identity does not trigger that pruning.
