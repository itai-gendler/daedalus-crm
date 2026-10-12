---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes suspend sync team for the case “Stop push/pull without deleting local files”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::sync-teams"
        }
      }
    },
    {
      "text": "Stop push/pull without deleting local files. Stops service push/pull without deleting local copies.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "changes",
          "facts": [
            "Active"
          ],
          "from": "Active",
          "to": "Suspended"
        }
      ],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::sync-teams"
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

# Stop push/pull without deleting local files

## Trigger

The operator invokes suspend sync team for the case “Stop push/pull without deleting local files”.

## Outcome

Stop push/pull without deleting local files. Stops service push/pull without deleting local copies.
