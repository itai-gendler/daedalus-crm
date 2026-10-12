---
{
  "kind": "validation",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator requests the account list or selected account detail.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::accounts"
        }
      }
    },
    {
      "text": "The submitted request reaches this validation boundary: Operator gate.",
      "kind": "condition",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::accounts"
        }
      }
    },
    {
      "text": "Failed operations entry produces the operations-gate refusal; the requested console result or action is not reported successful.",
      "kind": "product",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::accounts"
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

# Operator gate

## Trigger

The operator requests the account list or selected account detail.

## Outcome

Failed operations entry produces the operations-gate refusal; the requested console result or action is not reported successful.
