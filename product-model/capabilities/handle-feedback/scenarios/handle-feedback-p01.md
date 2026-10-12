---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes handle feedback for the case “Mark handled”.",
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
      "text": "Mark handled. Marks the selected feedback handled without sending mail; reopening is a separate capability.",
      "kind": "product",
      "entities": [
        {
          "entity": "feedback",
          "effect": "changes",
          "facts": [
            "Handled"
          ],
          "from": "Unhandled",
          "to": "Handled"
        }
      ],
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

# Mark handled

## Trigger

The operator invokes handle feedback for the case “Mark handled”.

## Outcome

Mark handled. Marks the selected feedback handled without sending mail; reopening is a separate capability.
