---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "channel",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-desktop::crm::channels"
        },
        {
          "place": "crm-web::crm::channels"
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

# Only CRM administrators, sales managers and salespeople may remove 渠道

This Rule governs remove operations on 渠道 at crm-desktop::crm::channels and crm-web::crm::channels.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
