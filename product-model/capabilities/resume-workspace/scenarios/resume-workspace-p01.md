---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes resume workspace for the case “Return to trial and recompute validity”.",
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
      "text": "Return to trial and recompute validity. Returns to TRIAL and recomputes validity; an already expired prior date can remain unwritable.",
      "kind": "product",
      "entities": [
        {
          "entity": "workspace",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "from": "SUSPENDED",
          "to": "TRIAL"
        }
      ],
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

# Return to trial and recompute validity

## Trigger

The operator invokes resume workspace for the case “Return to trial and recompute validity”.

## Outcome

Return to trial and recompute validity. Returns to TRIAL and recomputes validity; an already expired prior date can remain unwritable.
