---
{
  "kind": "validation",
  "routes": {
    "do": "Native operations"
  },
  "steps": [
    {
      "text": "The submitted request reaches this validation boundary: Operator identity/token rejection.",
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
      "text": "The request meets the named refusal boundary: Operator identity/token rejection.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "do": {
          "place": "crm-desktop::operations"
        }
      }
    },
    {
      "text": "Rejected operations identity/token suppresses the native operations feed; another account's notices are not delivered.",
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

# Operator identity/token rejection

## Trigger

The submitted request reaches this validation boundary: Operator identity/token rejection.

## Outcome

Rejected operations identity/token suppresses the native operations feed; another account's notices are not delivered.
