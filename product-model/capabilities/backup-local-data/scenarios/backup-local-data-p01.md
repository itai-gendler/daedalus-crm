---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes backup local data for the case “Manual consistent backup”.",
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
      "text": "Manual consistent backup. Creates a consistent integrity-checked immutable snapshot. Automatic meaningful-data daily/upgrade copies have retention; failure does not block startup. A manual target must not overwrite the current database.",
      "kind": "product",
      "entities": [
        {
          "entity": "backup",
          "effect": "creates",
          "facts": [
            "Time",
            "Class",
            "Location",
            "Size",
            "Snapshot"
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

# Manual consistent backup

## Trigger

A CRM member invokes backup local data for the case “Manual consistent backup”.

## Outcome

Manual consistent backup. Creates a consistent integrity-checked immutable snapshot. Automatic meaningful-data daily/upgrade copies have retention; failure does not block startup. A manual target must not overwrite the current database.
