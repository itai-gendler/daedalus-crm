---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "order",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::conversation"
        },
        {
          "place": "crm-desktop::crm::signing"
        },
        {
          "place": "crm-web::crm::conversation"
        },
        {
          "place": "crm-web::crm::signing"
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

# Only CRM administrators, sales managers and salespeople may create 订单

This Rule governs create operations on 订单 at crm-desktop::crm::conversation, crm-desktop::crm::signing, crm-web::crm::conversation and crm-web::crm::signing.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
