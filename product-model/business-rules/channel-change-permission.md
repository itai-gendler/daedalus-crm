---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "channel",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::channels"
        },
        {
          "place": "crm-web::crm::channels"
        },
        {
          "place": "crm-web::crm::conversation"
        },
        {
          "place": "crm-desktop::crm::conversation"
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

# Only CRM administrators, sales managers and salespeople may change 渠道

This Rule governs change operations on 渠道 at crm-desktop::crm::channels, crm-web::crm::channels, crm-web::crm::conversation and crm-desktop::crm::conversation.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
