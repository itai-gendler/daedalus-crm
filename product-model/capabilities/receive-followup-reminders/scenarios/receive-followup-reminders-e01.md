---
{
  "kind": "edge",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The scheduled or page-triggered service/OS delivery failure condition is reached.",
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
      "text": "Service or operating-system delivery failure does not promise a delivered notification.",
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

# Service/OS delivery failure

## Trigger

The scheduled or page-triggered service/OS delivery failure condition is reached.

## Outcome

Service or operating-system delivery failure does not promise a delivered notification.
