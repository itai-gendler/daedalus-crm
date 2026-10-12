---
{
  "kind": "edge",
  "routes": {
    "dp": "Native public",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A background check reaches unavailable release sources.",
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
      "text": "The background check can return no newer release and idle state when source lookup produces no candidate; this does not prove no release exists.",
      "kind": "product",
      "entities": [],
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

# Unavailable source may show no newer release

## Trigger

A background check reaches unavailable release sources.

## Outcome

The background check can return no newer release and idle state when source lookup produces no candidate; this does not prove no release exists.
