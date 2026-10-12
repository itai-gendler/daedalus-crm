---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "import-batch",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::customer-import"
        },
        {
          "place": "crm-web::crm::customer-import"
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

# Only CRM administrators, sales managers and salespeople may create 导入批次

This Rule governs create operations on 导入批次 at crm-desktop::crm::customer-import and crm-web::crm::customer-import.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
