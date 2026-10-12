---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes join team for the case “Join/reconcile identity”.",
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
      "text": "Join/reconcile identity. Checks fresh invite, member/device identity, keys/signatures and other-team exclusion. Reconciles CRM identity; same-team fresh invite can update keys instead of creating another membership.",
      "kind": "product",
      "entities": [
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
          "to": "Joined"
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

# Join/reconcile identity

## Trigger

A CRM member invokes join team for the case “Join/reconcile identity”.

## Outcome

Join/reconcile identity. Checks fresh invite, member/device identity, keys/signatures and other-team exclusion. Reconciles CRM identity; same-team fresh invite can update keys instead of creating another membership.
