---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "opportunity",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::conversation"
        },
        {
          "place": "crm-desktop::crm::opportunities"
        },
        {
          "place": "crm-web::crm::conversation"
        },
        {
          "place": "crm-web::crm::opportunities"
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

# Only CRM administrators, sales managers and salespeople may create 商机

This Rule governs create operations on 商机 at crm-desktop::crm::conversation, crm-desktop::crm::opportunities, crm-web::crm::conversation and crm-web::crm::opportunities.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
