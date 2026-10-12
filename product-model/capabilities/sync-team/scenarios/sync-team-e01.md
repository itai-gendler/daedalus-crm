---
{
  "kind": "edge",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes sync team for the case “Offline/schema/conflict/skipped/resumable result”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "Offline or key failures retain the bound team’s error/resume information; schema change retries once immediately. Missing keys wait, other corrupt packets skip after three attempts, field-clock conflicts remain partial, and returned batches replay without a fresh membership/activation query for each row.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "changes",
          "facts": [
            "Sync state"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/client.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/sync-relay.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/sync-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/device-token.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/desktop/sync/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/sync.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/local.ts"
    }
  ]
}
---

# Offline/schema/conflict/skipped/resumable result

## Trigger

A CRM member invokes sync team for the case “Offline/schema/conflict/skipped/resumable result”.

## Outcome

Offline or key failures retain the bound team’s error/resume information; schema change retries once immediately. Missing keys wait, other corrupt packets skip after three attempts, field-clock conflicts remain partial, and returned batches replay without a fresh membership/activation query for each row.
