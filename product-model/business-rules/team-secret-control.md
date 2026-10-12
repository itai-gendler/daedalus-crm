---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "sync-team",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::team"
        }
      ],
      "facts": [
        "Invite/key generation"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "created",
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
          "verb": "created",
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
          "verb": "created",
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
      "target": "src/lib/sync/tables.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/gateway-auth.ts"
    }
  ]
}
---

# Only related CRM administrators, related sales managers and related salespeople may change 同步团队

This Rule governs change operations on 同步团队 affecting Invite/key generation at crm-desktop::crm::team.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through Crm Account (created) → 系统管理员 / 老板 (holds).
- The sales managers reached through Crm Account (created) → 销售主管 (holds).
- The salespeople reached through Crm Account (created) → 销售 (holds).
