---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The scheduled or page-triggered daily summary condition is reached.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm"
        }
      },
      "unattended": true
    },
    {
      "text": "Daily summary. Current identity’s assigned unfinished work drives due notices, daily summaries and sleep-missed aggregation/badge. Cursors deduplicate; OS delivery is not assured.",
      "kind": "product",
      "entities": [
        {
          "entity": "desktop-config",
          "effect": "changes",
          "facts": [
            "Reminder cursor"
          ]
        },
        {
          "entity": "plan",
          "effect": "reads",
          "facts": [
            "Subject",
            "Planned time",
            "Owner",
            "Done"
          ]
        },
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Title",
            "Due time",
            "Owner",
            "Done"
          ]
        }
      ],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/main.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/backup.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/auto-backup.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/updater.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/reminders.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/landing.ts"
    }
  ]
}
---

# Daily summary

## Trigger

The scheduled or page-triggered daily summary condition is reached.

## Outcome

Daily summary. Current identity’s assigned unfinished work drives due notices, daily summaries and sleep-missed aggregation/badge. Cursors deduplicate; OS delivery is not assured.
