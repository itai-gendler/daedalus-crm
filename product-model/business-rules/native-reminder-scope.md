---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "receive-followup-reminders"
    },
    {
      "type": "capability",
      "id": "change-desktop-settings"
    },
    {
      "type": "entity",
      "id": "desktop-config"
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

# Native reminders use the current identity's assigned unfinished work

The due notice and daily summary inspect unfinished work assigned to the current identity under its saved reminder preferences. The implementation retains timing, deduplication and sleep-missed aggregation. A generated notice is not proof of operating-system delivery.
