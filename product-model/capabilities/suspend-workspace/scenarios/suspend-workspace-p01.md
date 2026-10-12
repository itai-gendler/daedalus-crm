---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes suspend workspace for the case “Suspend and retain data”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::workspaces"
        }
      }
    },
    {
      "text": "Suspend and retain data. Sets SUSPENDED and retains data.",
      "kind": "product",
      "entities": [
        {
          "entity": "workspace",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "from": "ACTIVE",
          "to": "SUSPENDED"
        }
      ],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::workspaces"
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

# Suspend and retain data

## Trigger

The operator invokes suspend workspace for the case “Suspend and retain data”.

## Outcome

Suspend and retain data. Sets SUSPENDED and retains data.
