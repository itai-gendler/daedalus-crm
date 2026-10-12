---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "feedback",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::feedback"
        },
        {
          "place": "crm-web::crm::feedback"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "operator"
      ]
    },
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

# Only operations staff and CRM administrators, sales managers and salespeople may create 反馈

This Rule governs create operations on 反馈 at crm-desktop::crm::feedback and crm-web::crm::feedback.

The selected operation can pass through any one of these grants:

- Operations staff.
- CRM administrators, sales managers and salespeople.
