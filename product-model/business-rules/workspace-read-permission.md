---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "workspace",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm::subscription"
        },
        {
          "place": "crm-web::operations::workspaces"
        },
        {
          "place": "crm-web::public::login"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "contains",
          "entity": "workspace-membership"
        },
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
          "verb": "contains",
          "entity": "workspace-membership"
        },
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
          "verb": "contains",
          "entity": "workspace-membership"
        },
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

# Only related CRM administrators, related sales managers, related salespeople and operations staff may read 工作区

This Rule governs read operations on 工作区 at crm-web::crm::subscription, crm-web::operations::workspaces and crm-web::public::login.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through Workspace Membership (contains) → Crm Account (identifies) → 系统管理员 / 老板 (holds).
- The sales managers reached through Workspace Membership (contains) → Crm Account (identifies) → 销售主管 (holds).
- The salespeople reached through Workspace Membership (contains) → Crm Account (identifies) → 销售 (holds).
- Operations staff.
