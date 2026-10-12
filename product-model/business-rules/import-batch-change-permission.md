---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "import-batch",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::import-history"
        },
        {
          "place": "crm-web::crm::import-history"
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

# Only CRM administrators, sales managers and salespeople may change 导入批次

This Rule governs change operations on 导入批次 at crm-desktop::crm::import-history and crm-web::crm::import-history.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
