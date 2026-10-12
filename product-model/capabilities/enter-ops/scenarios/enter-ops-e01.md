---
{
  "kind": "edge",
  "routes": {
    "wo": "Web operations",
    "do": "Native operations"
  },
  "steps": [
    {
      "text": "The operator invokes enter ops for the case “Expired/used code or network failure”.",
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
      "text": "The dependency or network error is shown; the interface does not claim that the requested save completed.",
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

# Expired/used code or network failure

## Trigger

The operator invokes enter ops for the case “Expired/used code or network failure”.

## Outcome

The dependency or network error is shown; the interface does not claim that the requested save completed.
