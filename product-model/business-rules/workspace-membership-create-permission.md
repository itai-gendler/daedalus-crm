---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "workspace-membership",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::operations::workspaces"
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
        "crm-admin",
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

# Only related CRM administrators, related sales managers, related salespeople and CRM administrators and operations staff may create Workspace Membership

This Rule governs create operations on Workspace Membership at crm-web::operations::workspaces.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through Crm Account (identifies) → 系统管理员 / 老板 (holds).
- The sales managers reached through Crm Account (identifies) → 销售主管 (holds).
- The salespeople reached through Crm Account (identifies) → 销售 (holds).
- CRM administrators and operations staff.
