---
{
  "kind": "validation",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The submitted request reaches this validation boundary: Identity/settings suppress notice.",
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
      "text": "The request meets the named refusal boundary: Identity/settings suppress notice.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "da": {
          "place": "crm-desktop::crm"
        }
      }
    },
    {
      "text": "The inspected identity/reminder settings suppress notification; no notice is represented as delivered through this suppressed run.",
      "kind": "product",
      "entities": [],
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

# Identity/settings suppress notice

## Trigger

The submitted request reaches this validation boundary: Identity/settings suppress notice.

## Outcome

The inspected identity/reminder settings suppress notification; no notice is represented as delivered through this suppressed run.
