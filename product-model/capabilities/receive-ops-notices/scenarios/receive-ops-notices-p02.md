---
{
  "kind": "primary",
  "routes": {
    "do": "Native operations"
  },
  "steps": [
    {
      "text": "The scheduled or page-triggered usage/pending-team notices condition is reached.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "do": {
          "place": "crm-desktop::operations"
        }
      },
      "unattended": true
    },
    {
      "text": "Usage/pending-team notices. Native first start skips notice history; two-minute polling catches up 24 hours with two-day dedup and safe destinations. Offline cursors remain and OS delivery is not exactly once.",
      "kind": "product",
      "entities": [
        {
          "entity": "desktop-config",
          "effect": "changes",
          "facts": [
            "Operations cursor"
          ]
        }
      ],
      "contexts": {
        "do": {
          "place": "crm-desktop::operations"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/data.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/guard.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ops-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/ops-notices.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/feedback-reply.ts"
    }
  ]
}
---

# Usage/pending-team notices

## Trigger

The scheduled or page-triggered usage/pending-team notices condition is reached.

## Outcome

Usage/pending-team notices. Native first start skips notice history; two-minute polling catches up 24 hours with two-day dedup and safe destinations. Offline cursors remain and OS delivery is not exactly once.
