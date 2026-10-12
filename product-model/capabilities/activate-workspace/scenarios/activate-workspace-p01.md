---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes activate workspace for the case “Activate/renew plan”.",
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
      "text": "Activate/renew plan. Activates or renews the selected valid plan; this is separate from payment-reference submission.",
      "kind": "product",
      "entities": [
        {
          "entity": "workspace",
          "effect": "changes",
          "facts": [
            "Status",
            "Plan",
            "Trial expiry",
            "Paid expiry",
            "Notes"
          ],
          "from": "TRIAL",
          "to": "ACTIVE"
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

# Activate/renew plan

## Trigger

The operator invokes activate workspace for the case “Activate/renew plan”.

## Outcome

Activate/renew plan. Activates or renews the selected valid plan; this is separate from payment-reference submission.
