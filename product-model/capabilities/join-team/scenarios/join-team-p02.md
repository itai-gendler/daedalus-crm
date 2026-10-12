---
{
  "kind": "primary",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes join team for the case “Same-team fresh invite updates keys”.",
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
      "text": "Same-team fresh invite updates keys. Checks fresh invite, member/device identity, keys/signatures and other-team exclusion. Reconciles CRM identity; same-team fresh invite can update keys instead of creating another membership.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "changes",
          "facts": [
            "Invite/key generation"
          ]
        },
        {
          "entity": "sync-membership",
          "effect": "changes",
          "facts": [
            "Device participation"
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

# Same-team fresh invite updates keys

## Trigger

A CRM member invokes join team for the case “Same-team fresh invite updates keys”.

## Outcome

Same-team fresh invite updates keys. Checks fresh invite, member/device identity, keys/signatures and other-team exclusion. Reconciles CRM identity; same-team fresh invite can update keys instead of creating another membership.
