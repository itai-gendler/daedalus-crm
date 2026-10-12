---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "schedule-followup"
    },
    {
      "type": "capability",
      "id": "edit-schedule"
    },
    {
      "type": "capability",
      "id": "complete-schedule"
    },
    {
      "type": "capability",
      "id": "reopen-schedule"
    },
    {
      "type": "capability",
      "id": "delete-schedule"
    },
    {
      "type": "entity",
      "id": "plan"
    },
    {
      "type": "entity",
      "id": "task"
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

# Plans append and remain separate from tasks

Creating a plan appends a distinct arrangement without replacing existing plans. Manual arrangements retain the creator as owner. Tasks keep their completion time; plans expose completion using their retained last change instead of an invented completion-time fact.
