---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "customer",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::customer-import"
        },
        {
          "place": "crm-desktop::crm::customers"
        },
        {
          "place": "crm-desktop::crm::leads"
        },
        {
          "place": "crm-web::crm::customer-import"
        },
        {
          "place": "crm-web::crm::customers"
        },
        {
          "place": "crm-web::crm::data"
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

# Only CRM administrators, sales managers and salespeople may create 客户

This Rule governs create operations on 客户 at crm-desktop::crm::customer-import, crm-desktop::crm::customers, crm-desktop::crm::leads, crm-web::crm::customer-import, crm-web::crm::customers, crm-web::crm::data and crm-web::crm::leads.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
