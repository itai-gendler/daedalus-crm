---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse local data for the case “Account allowance/version/directories/logs/backups”.",
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
      "text": "Account allowance/version/directories/logs/backups. Shows local account allowance, version, data/log directories and available backups; older bridge or cloud/list failures are visible.",
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
        },
        {
          "entity": "backup",
          "effect": "reads",
          "facts": [
            "Time",
            "Class",
            "Location",
            "Size"
          ]
        },
        {
          "entity": "cloud-account",
          "effect": "reads",
          "facts": [
            "AI allowance"
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

# Account allowance/version/directories/logs/backups

## Trigger

A CRM member invokes browse local data for the case “Account allowance/version/directories/logs/backups”.

## Outcome

Account allowance/version/directories/logs/backups. Shows local account allowance, version, data/log directories and available backups; older bridge or cloud/list failures are visible.
