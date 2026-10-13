---
{
  "kind": "primary",
  "routes": {
    "dp": "Native public",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The native client’s retained Data mode is Server, so returning to local data is offered.",
      "kind": "condition",
      "entities": [
        {
          "entity": "desktop-config",
          "effect": "reads",
          "facts": [
            "Data mode"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "dp": {
          "place": "crm-desktop::public::server-connection"
        },
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      }
    },
    {
      "text": "A CRM member invokes change desktop settings for the case “Return from chosen server to local data”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "dp": {
          "place": "crm-desktop::public::server-connection"
        },
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      }
    },
    {
      "text": "The native client returns to the owned local book without signing into the chosen site. Reminder preferences and the test notification stay in local settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "desktop-config",
          "effect": "changes",
          "facts": [
            "Data mode"
          ],
          "from": "Server",
          "to": "Local"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "dp": {
          "place": "crm-desktop::public::server-connection"
        },
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
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

# Return from chosen server to local data

## Trigger

A CRM member invokes change desktop settings for the case “Return from chosen server to local data”.

## Outcome

The native client returns to the owned local book without signing into the chosen site. Reminder preferences and the test notification stay in local settings.
