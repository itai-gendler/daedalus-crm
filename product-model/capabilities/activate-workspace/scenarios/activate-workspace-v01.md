---
{
  "kind": "validation",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes activate workspace for the case “Plan/target/operator rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Plan/target/operator rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::workspaces"
        }
      }
    },
    {
      "text": "An invalid plan, unavailable workspace or failed operations entry returns the activation refusal; no renewal is reported granted.",
      "kind": "product",
      "entities": [],
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

# Plan/target/operator rejection

## Trigger

The operator invokes activate workspace for the case “Plan/target/operator rejection”.

## Outcome

An invalid plan, unavailable workspace or failed operations entry returns the activation refusal; no renewal is reported granted.
