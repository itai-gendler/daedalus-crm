---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "backup",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm"
        },
        {
          "place": "crm-desktop::crm"
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
    },
    {
      "unattended": true
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

# Only CRM administrators, sales managers and salespeople and the Product's scheduled process may create 备份

This Rule governs create operations on 备份 at crm-web::crm and crm-desktop::crm.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
- The Product's scheduled process.
