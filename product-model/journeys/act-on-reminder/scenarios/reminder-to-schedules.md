---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "da": "DA"
  },
  "steps": [
    {
      "text": "Activate the follow-up summary or badge destination.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm"
        }
      },
      "capability": "receive-followup-reminders"
    },
    {
      "text": "Summary notification activation carries the arrangement destination to schedules.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "reads",
          "facts": [
            "Subject",
            "Planned time",
            "Owner",
            "Done"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm"
        }
      },
      "capability": "receive-followup-reminders"
    },
    {
      "text": "Inspect the carried arrangement scope.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::schedules"
        }
      },
      "capability": "browse-schedules"
    },
    {
      "text": "The activated destination presents the applicable unfinished plans and tasks; a summary carries the arrangement scope instead of inventing one selected customer.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "reads",
          "facts": [
            "Subject",
            "Planned time",
            "Method",
            "Owner",
            "Done",
            "Created time",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::schedules"
        }
      },
      "capability": "browse-schedules"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/reminders.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/main.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/desktop/reminders/route.ts"
    }
  ]
}
---

# Reminder To Schedules

## Trigger

Summary notification activation carries the arrangement destination to schedules.

## Outcome

The activated destination presents the applicable unfinished plans and tasks; a summary carries the arrangement scope instead of inventing one selected customer.
