---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "supplier",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm::signing"
        },
        {
          "place": "crm-desktop::crm::signing"
        },
        {
          "place": "crm-web::crm::order-record"
        },
        {
          "place": "crm-desktop::crm::order-record"
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

# Only CRM administrators, sales managers and salespeople may read 供应商

This Rule governs read operations on 供应商 at crm-web::crm::signing, crm-desktop::crm::signing, crm-web::crm::order-record and crm-desktop::crm::order-record.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
