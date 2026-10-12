---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "assigned-contact",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::contacts"
        },
        {
          "place": "crm-desktop::crm::customer-record"
        },
        {
          "place": "crm-web::crm::contacts"
        },
        {
          "place": "crm-web::crm::customer-record"
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

# Only CRM administrators, sales managers and salespeople may create 客户联系人

This Rule governs create operations on 客户联系人 at crm-desktop::crm::contacts, crm-desktop::crm::customer-record, crm-web::crm::contacts and crm-web::crm::customer-record.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
