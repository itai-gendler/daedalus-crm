---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes mark test account for the case “Mark and retain history”.",
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
      "text": "Mark and retain history. Changes the manual test marker and records its history. Configured operator identities remain inherently test/unlimited even after the manual marker is removed.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "changes",
          "facts": [
            "Test marker",
            "Test history"
          ]
        }
      ],
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

# Mark and retain history

## Trigger

The operator invokes mark test account for the case “Mark and retain history”.

## Outcome

Mark and retain history. Changes the manual test marker and records its history. Configured operator identities remain inherently test/unlimited even after the manual marker is removed.
