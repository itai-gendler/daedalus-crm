---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "lead",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::conversation"
        },
        {
          "place": "crm-desktop::crm::leads"
        },
        {
          "place": "crm-web::crm::conversation"
        },
        {
          "place": "crm-web::crm::leads"
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

# Only CRM administrators, sales managers and salespeople may create 线索

This Rule governs create operations on 线索 at crm-desktop::crm::conversation, crm-desktop::crm::leads, crm-web::crm::conversation and crm-web::crm::leads.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
