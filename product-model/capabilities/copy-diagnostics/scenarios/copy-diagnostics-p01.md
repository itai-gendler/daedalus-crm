---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes copy diagnostics for the case “Copy state/log-location information”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      }
    },
    {
      "text": "Copy state/log-location information. Copies native state and log-location information; a missing bridge or clipboard error is visible.",
      "kind": "product",
      "entities": [
        {
          "entity": "desktop-config",
          "effect": "reads",
          "facts": [
            "Data mode",
            "Server address",
            "Data location",
            "Account binding",
            "Current team binding",
            "Remembered route",
            "Reminder preferences",
            "Reminder cursor",
            "Operations cursor",
            "Update state",
            "Update version/method",
            "Client version"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
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

# Copy state/log-location information

## Trigger

A CRM member invokes copy diagnostics for the case “Copy state/log-location information”.

## Outcome

Copy state/log-location information. Copies native state and log-location information; a missing bridge or clipboard error is visible.
