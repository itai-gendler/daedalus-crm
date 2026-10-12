---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes reply feedback for the case “Send mail, then save reply/handled state”.",
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
      "text": "Send mail, then save reply/handled state. Checks recipient/body and sends mail before persisting the reply and handled state. SMTP failure saves nothing; persistence failure after sending can leave unrecorded mail.",
      "kind": "product",
      "entities": [
        {
          "entity": "feedback",
          "effect": "changes",
          "facts": [
            "Replies",
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

# Send mail, then save reply/handled state

## Trigger

The operator invokes reply feedback for the case “Send mail, then save reply/handled state”.

## Outcome

Send mail, then save reply/handled state. Checks recipient/body and sends mail before persisting the reply and handled state. SMTP failure saves nothing; persistence failure after sending can leave unrecorded mail.
