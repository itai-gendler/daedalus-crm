---
{
  "kind": "validation",
  "routes": {
    "wo": "Web operations",
    "do": "Native operations"
  },
  "steps": [
    {
      "text": "The operator invokes enter ops for the case “Operator/deployment rejection”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations"
        },
        "do": {
          "place": "crm-desktop::operations"
        }
      }
    },
    {
      "text": "The submitted request reaches this validation boundary: Operator/deployment rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations"
        },
        "do": {
          "place": "crm-desktop::operations"
        }
      }
    },
    {
      "text": "Invalid operations entry or an unavailable operations deployment refuses console entry and issues no usable operations session.",
      "kind": "product",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations"
        },
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

# Operator/deployment rejection

## Trigger

The operator invokes enter ops for the case “Operator/deployment rejection”.

## Outcome

Invalid operations entry or an unavailable operations deployment refuses console entry and issues no usable operations session.
