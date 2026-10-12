---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "business-config",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm::business-settings"
        },
        {
          "place": "crm-desktop::crm::business-settings"
        },
        {
          "place": "crm-desktop::crm::initial-template"
        },
        {
          "place": "crm-web::crm::customer-import"
        },
        {
          "place": "crm-desktop::crm::customer-import"
        },
        {
          "place": "crm-web::crm::signing"
        },
        {
          "place": "crm-desktop::crm::signing"
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

# Only CRM administrators, sales managers and salespeople may read 业务设置

This Rule governs read operations on 业务设置 at crm-web::crm::business-settings, crm-desktop::crm::business-settings, crm-desktop::crm::initial-template, crm-web::crm::customer-import, crm-desktop::crm::customer-import, crm-web::crm::signing and crm-desktop::crm::signing.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
