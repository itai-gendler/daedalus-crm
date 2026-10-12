---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes activate sync team for the case “Activate and replace activation time”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::sync-teams"
        }
      }
    },
    {
      "text": "Activate and replace activation time. Sets service Active and replaces the activation timestamp on every activation.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "changes",
          "facts": [
            "Active",
            "Activation time"
          ],
          "from": "Waiting",
          "to": "Active"
        }
      ],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::sync-teams"
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

# Activate and replace activation time

## Trigger

The operator invokes activate sync team for the case “Activate and replace activation time”.

## Outcome

Activate and replace activation time. Sets service Active and replaces the activation timestamp on every activation.
