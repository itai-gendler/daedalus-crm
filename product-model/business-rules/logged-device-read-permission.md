---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "logged-device",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm::password"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "cloud-account"
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
          "verb": "owns",
          "entity": "cloud-account"
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
          "verb": "owns",
          "entity": "cloud-account"
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

# Only related CRM administrators, related sales managers and related salespeople may read 登录设备

This Rule governs read operations on 登录设备 at crm-web::crm::password.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through Cloud Account (owns) → Crm Account (identifies) → 系统管理员 / 老板 (holds).
- The sales managers reached through Cloud Account (owns) → Crm Account (identifies) → 销售主管 (holds).
- The salespeople reached through Cloud Account (owns) → Crm Account (identifies) → 销售 (holds).
