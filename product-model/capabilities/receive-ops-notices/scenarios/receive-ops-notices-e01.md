---
{
  "kind": "edge",
  "routes": {
    "do": "Native operations"
  },
  "steps": [
    {
      "text": "The scheduled or page-triggered offline cursor retained condition is reached.",
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
      "text": "Offline cursor is retained; first start skips old history and delivery remains best effort.",
      "kind": "product",
      "entities": [],
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

# Offline cursor retained

## Trigger

The scheduled or page-triggered offline cursor retained condition is reached.

## Outcome

Offline cursor is retained; first start skips old history and delivery remains best effort.
