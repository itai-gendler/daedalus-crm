---
{
  "kind": "primary",
  "routes": {
    "dp": "Native public",
    "da": "Native CRM"
  },
  "steps": [
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
      "text": "Return from chosen server to local data. Native server connection takes a validated address; return-local works without signing into the chosen site and reopens the owned local book. Reminder preferences/test notification stay in local settings.",
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

Return from chosen server to local data. Native server connection takes a validated address; return-local works without signing into the chosen site and reopens the owned local book. Reminder preferences/test notification stay in local settings.
