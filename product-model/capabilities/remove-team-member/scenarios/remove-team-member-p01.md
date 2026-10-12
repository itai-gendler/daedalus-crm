---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes remove team member for the case “Creator removal with invite/key rotation”.",
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
      "text": "Creator removal with invite/key rotation. Creator removal records departure and rotates invite/data keys. Machine authority is checked; membership removal can succeed before key redistribution fails.",
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
        },
        {
          "entity": "sync-team",
          "effect": "changes",
          "facts": [
            "Invite/key generation"
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

# Creator removal with invite/key rotation

## Trigger

A CRM member invokes remove team member for the case “Creator removal with invite/key rotation”.

## Outcome

Creator removal with invite/key rotation. Creator removal records departure and rotates invite/data keys. Machine authority is checked; membership removal can succeed before key redistribution fails.
