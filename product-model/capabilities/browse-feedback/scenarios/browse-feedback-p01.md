---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes browse feedback for the case “Feedback/handling/replies”.",
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
      "text": "Feedback/handling/replies. Shows at most 300 feedback items, their handled state and reply history.",
      "kind": "product",
      "entities": [
        {
          "entity": "feedback",
          "effect": "reads",
          "facts": [
            "Body",
            "Page",
            "Version",
            "System",
            "Account/contact",
            "Submitted time",
            "Handled",
            "Replies"
          ]
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

# Feedback/handling/replies

## Trigger

The operator invokes browse feedback for the case “Feedback/handling/replies”.

## Outcome

Feedback/handling/replies. Shows at most 300 feedback items, their handled state and reply history.
