---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "unassigned-contact",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-desktop::crm::contacts"
        },
        {
          "place": "crm-web::crm::contacts"
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

# Only CRM administrators, sales managers and salespeople may read 未关联联系人

This Rule governs read operations on 未关联联系人 at crm-desktop::crm::contacts and crm-web::crm::contacts.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
