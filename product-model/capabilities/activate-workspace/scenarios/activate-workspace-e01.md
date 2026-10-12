---
{
  "kind": "edge",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes activate workspace for the case “Database failure”.",
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
      "text": "A failed workspace update is exposed instead of reporting successful activation or renewal; the requested status, paid expiry and activation note are not confirmed saved.",
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

# Database failure

## Trigger

The operator invokes activate workspace for the case “Database failure”.

## Outcome

A failed workspace update is exposed instead of reporting successful activation or renewal; the requested status, paid expiry and activation note are not confirmed saved.
