---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes create team for the case “Create waiting team and reveal invite”.",
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
      "text": "Create waiting team and reveal invite. Creates a waiting team from the cloud-bound local identity and reveals its invite. One local team and actual name/team-count constraints apply.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "creates",
          "facts": [
            "Name",
            "Active",
            "Activation time",
            "Invite/key generation",
            "Creator",
            "Sync state"
          ],
          "to": "Waiting"
        },
        {
          "entity": "sync-membership",
          "effect": "creates",
          "facts": [
            "Member identity",
            "Role",
            "Joined time",
            "Left time",
            "Device participation"
          ],
          "to": "Joined",
          "with": "sync-team"
        },
        {
          "entity": "crm-account",
          "effect": "changes",
          "facts": [
            "Role assignment",
            "Name",
            "Login",
            "Last change"
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

# Create waiting team and reveal invite

## Trigger

A CRM member invokes create team for the case “Create waiting team and reveal invite”.

## Outcome

Create waiting team and reveal invite. Creates a waiting team from the cloud-bound local identity and reveals its invite. One local team and actual name/team-count constraints apply.
