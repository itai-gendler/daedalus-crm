---
{
  "kind": "edge",
  "routes": {
    "dp": "Native public",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes change desktop settings for the case “Connection failure/unsupported notification system”.",
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
      "text": "An unreachable chosen server reports connection failure rather than adopting its site as a working local book. Unsupported operating-system notifications or an absent bridge do not report successful delivery of the test notification.",
      "kind": "product",
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

# Connection failure/unsupported notification system

## Trigger

A CRM member invokes change desktop settings for the case “Connection failure/unsupported notification system”.

## Outcome

An unreachable chosen server reports connection failure rather than adopting its site as a working local book. Unsupported operating-system notifications or an absent bridge do not report successful delivery of the test notification.
