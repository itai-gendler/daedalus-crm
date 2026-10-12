---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "sync-membership",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm"
        },
        {
          "place": "crm-desktop::crm"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin",
        "crm-manager",
        "crm-sales"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/mcp/tools.ts"
    }
  ]
}
---

# Only CRM administrators, sales managers and salespeople may create Sync Membership

This Rule governs create operations on Sync Membership at crm-web::crm and crm-desktop::crm.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
