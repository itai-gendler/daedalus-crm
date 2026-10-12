---
{
  "kind": "primary",
  "routes": {
    "dp": "Native public",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The scheduled or page-triggered startup/upgrade automatic backup condition is reached.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "dp": {
          "place": "crm-desktop::public"
        },
        "da": {
          "place": "crm-desktop::crm::desktop-settings"
        }
      },
      "unattended": true
    },
    {
      "text": "Startup/upgrade automatic backup. Creates a consistent integrity-checked immutable snapshot. Automatic meaningful-data daily/upgrade copies have retention; failure does not block startup. A manual target must not overwrite the current database.",
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
      "contexts": {
        "dp": {
          "place": "crm-desktop::public"
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

# Startup/upgrade automatic backup

## Trigger

The scheduled or page-triggered startup/upgrade automatic backup condition is reached.

## Outcome

Startup/upgrade automatic backup. Creates a consistent integrity-checked immutable snapshot. Automatic meaningful-data daily/upgrade copies have retention; failure does not block startup. A manual target must not overwrite the current database.


## Edge cases

- A missing/empty database skips automatic copies. The first recorded version establishes a marker rather than an upgrade copy; meaningful-data daily copies and detected-version-change copies retain their actual limits.
- The automatic destination is derived under this book’s backup directory; no human destination is requested in public startup. The active-database-overwrite refusal belongs to the separate manual destination case.
- Copy/schema/disk failure is caught and logged without blocking startup or claiming a new backup; existing copies are retained.
