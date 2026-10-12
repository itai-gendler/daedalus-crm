---
{
  "kind": "edge",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes remove team member for the case “Member removed but key redistribution incomplete”.",
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
      "text": "Departure can commit before key redistribution finishes; the error does not imply restored membership or reclaimed copies.",
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

# Member removed but key redistribution incomplete

## Trigger

A CRM member invokes remove team member for the case “Member removed but key redistribution incomplete”.

## Outcome

Departure can commit before key redistribution finishes; the error does not imply restored membership or reclaimed copies.
