---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes leave team for the case “Member leaves retaining own scoped data”.",
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
      "text": "Member leaves retaining own scoped data. Records departure and keeps own scoped local data for a known noncreator. A creator with members cannot leave; offline local exit and unknown-identity retention have distinct behavior.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-membership",
          "effect": "changes",
          "facts": [
            "Left time"
          ],
          "from": "Joined",
          "to": "Left"
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
      "target": "src/app/(app)/settings/team-actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/TeamTab.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/client.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/local.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/sync-relay.ts"
    }
  ]
}
---

# Member leaves retaining own scoped data

## Trigger

A CRM member invokes leave team for the case “Member leaves retaining own scoped data”.

## Outcome

Member leaves retaining own scoped data. Records departure and keeps own scoped local data for a known noncreator. A creator with members cannot leave; offline local exit and unknown-identity retention have distinct behavior.
