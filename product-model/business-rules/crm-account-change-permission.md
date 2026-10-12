---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "crm-account",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::customer-record"
        },
        {
          "place": "crm-desktop::crm::profile"
        },
        {
          "place": "crm-web::crm::customer-record"
        },
        {
          "place": "crm-web::crm::members"
        },
        {
          "place": "crm-web::crm::profile"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "holds",
          "entity": "crm-admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "crm-manager"
        }
      ]
    },
    {
      "related": [
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

# Only related CRM administrators, related sales managers, related salespeople and CRM administrators and operations staff may change Crm Account

This Rule governs change operations on Crm Account at crm-desktop::crm::customer-record, crm-desktop::crm::profile, crm-web::crm::customer-record, crm-web::crm::members and crm-web::crm::profile.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through 系统管理员 / 老板 (holds).
- The sales managers reached through 销售主管 (holds).
- The salespeople reached through 销售 (holds).
- CRM administrators and operations staff.
