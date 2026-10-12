---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "sync-membership",
      "effect": "reads",
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
      "related": [
        {
          "verb": "identifies",
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
          "verb": "identifies",
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
          "verb": "identifies",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    },
    {
      "actors": [
        "operator"
      ]
    },
    {
      "unattended": true,
      "when": [
        {
          "fact": "Left time",
          "absent": true
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

# Only related CRM administrators, related sales managers, related salespeople, operations staff and the Product's scheduled process may read Sync Membership

This Rule governs read operations on Sync Membership at crm-web::crm and crm-desktop::crm.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through Crm Account (identifies) → 系统管理员 / 老板 (holds).
- The sales managers reached through Crm Account (identifies) → 销售主管 (holds).
- The salespeople reached through Crm Account (identifies) → 销售 (holds).
- Operations staff.
- The Product's scheduled process, when Sync Membership.Left time is absent.
