---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "workspace",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm::subscription"
        }
      ],
      "facts": [
        "Payment references"
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
      ],
      "when": [
        {
          "entity": "workspace-membership",
          "fact": "Role",
          "is": "OWNER"
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
      ],
      "when": [
        {
          "entity": "workspace-membership",
          "fact": "Role",
          "is": "OWNER"
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
      ],
      "when": [
        {
          "entity": "workspace-membership",
          "fact": "Role",
          "is": "OWNER"
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

# Only related CRM administrators, related sales managers and related salespeople may change 工作区

This Rule governs change operations on 工作区 affecting Payment references at crm-web::crm::subscription.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through Workspace Membership (contains) → Crm Account (identifies) → 系统管理员 / 老板 (holds), when Workspace Membership.Role is OWNER.
- The sales managers reached through Workspace Membership (contains) → Crm Account (identifies) → 销售主管 (holds), when Workspace Membership.Role is OWNER.
- The salespeople reached through Workspace Membership (contains) → Crm Account (identifies) → 销售 (holds), when Workspace Membership.Role is OWNER.
