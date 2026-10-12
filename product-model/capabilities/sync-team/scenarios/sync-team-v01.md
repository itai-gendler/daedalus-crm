---
{
  "kind": "validation",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes sync team for the case “Membership/activation/key rejection”.",
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
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      },
      "text": "The Product prepares the bound book and inspects pending changes before the request meets its relay or key rejection.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "reads",
          "facts": [
            "Sync state"
          ]
        }
      ]
    },
    {
      "text": "The submitted request reaches this validation boundary: Membership/activation/key rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "The refused push/pull or failed key retrieval retains local error/time information for the same bound team, without reporting a successful exchange. Earlier preparation and already completed stages remain.",
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

# Membership/activation/key rejection

## Trigger

A CRM member invokes sync team for the case “Membership/activation/key rejection”.

## Outcome

The refused push/pull or failed key retrieval retains local error/time information for the same bound team, without reporting a successful exchange. Earlier preparation and already completed stages remain.

## Edge cases

- The selected relay team missing or caller membership absent/left yields 403; inactive selected team yields 402. Invalid/revoked device bearer fails recognition separately.
- Old key epoch refreshes and retries; future epoch is rejected. DT2 verifies retained signing identity and purpose; DT1 does not gain an extra signature check.
