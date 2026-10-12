---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse team for the case “Creator member overview/possible duplicates”.",
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
      "text": "Creator member overview/possible duplicates. Shows current team, members and sync state; creator overview can reveal possible duplicates. Offline, removal and waiting activation are distinct.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "reads",
          "facts": [
            "Name",
            "Active",
            "Activation time",
            "Invite/key generation",
            "Creator",
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

# Creator member overview/possible duplicates

## Trigger

A CRM member invokes browse team for the case “Creator member overview/possible duplicates”.

## Outcome

Creator member overview/possible duplicates. Shows current team, members and sync state; creator overview can reveal possible duplicates. Offline, removal and waiting activation are distinct.
