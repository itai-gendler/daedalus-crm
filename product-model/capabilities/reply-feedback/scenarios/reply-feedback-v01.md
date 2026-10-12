---
{
  "kind": "validation",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes reply feedback for the case “Recipient/body/target/operator rejection”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::feedback"
        }
      }
    },
    {
      "text": "The submitted request reaches this validation boundary: Recipient/body/target/operator rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::feedback"
        }
      }
    },
    {
      "text": "A missing feedback target, missing/invalid recipient, empty reply body or failed operations entry prevents a successful reply send and saved reply from being reported.",
      "kind": "product",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::feedback"
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

# Recipient/body/target/operator rejection

## Trigger

The operator invokes reply feedback for the case “Recipient/body/target/operator rejection”.

## Outcome

A missing feedback target, missing/invalid recipient, empty reply body or failed operations entry prevents a successful reply send and saved reply from being reported.
