---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "conversation",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::conversation"
        },
        {
          "place": "crm-desktop::crm::home"
        },
        {
          "place": "crm-web::crm::conversation"
        },
        {
          "place": "crm-web::crm::home"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-manager"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
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

# Only related CRM administrators, related sales managers and related salespeople may change 对话

This Rule governs change operations on 对话 at crm-desktop::crm::conversation, crm-desktop::crm::home, crm-web::crm::conversation and crm-web::crm::home.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through Crm Account (owns) → 系统管理员 / 老板 (holds).
- The sales managers reached through Crm Account (owns) → 销售主管 (holds).
- The salespeople reached through Crm Account (owns) → 销售 (holds).
