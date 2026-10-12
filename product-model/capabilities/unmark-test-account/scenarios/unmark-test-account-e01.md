---
{
  "kind": "edge",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes unmark test account for the case “Configured operator still unlimited/test”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::account-record"
        }
      }
    },
    {
      "text": "Removing the manual marker retains test history. A configured operations identity continues to be treated as test/unlimited, so removing the marker does not turn that identity into an ordinary billable account.",
      "kind": "product",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::account-record"
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

# Configured operator still unlimited/test

## Trigger

The operator invokes unmark test account for the case “Configured operator still unlimited/test”.

## Outcome

Removing the manual marker retains test history. A configured operations identity continues to be treated as test/unlimited, so removing the marker does not turn that identity into an ordinary billable account.
