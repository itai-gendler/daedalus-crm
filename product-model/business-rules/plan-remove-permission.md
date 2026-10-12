---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "plan",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-desktop::crm::schedules"
        },
        {
          "place": "crm-web::crm::schedules"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin",
        "crm-manager"
      ]
    },
    {
      "actors": [
        "crm-sales"
      ],
      "when": [
        {
          "entity": "service-config",
          "fact": "Hosting/native mode",
          "is-not": "desktop-local"
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
    },
    {
      "related": [
        {
          "verb": "has",
          "entity": "customer"
        },
        {
          "verb": "sales-owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has",
          "entity": "customer"
        },
        {
          "verb": "channel-owns",
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
        "crm-sales"
      ],
      "when": [
        {
          "entity": "customer",
          "fact": "Pool state",
          "is": "in"
        }
      ]
    },
    {
      "when": [
        {
          "entity": "desktop-config",
          "fact": "Current team binding",
          "absent": true
        }
      ],
      "related": [
        {
          "verb": "keeps",
          "entity": "desktop-config"
        },
        {
          "verb": "uses",
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

# Only CRM administrators and sales managers, salespeople and related salespeople may remove 跟进计划

This Rule governs remove operations on 跟进计划 at crm-desktop::crm::schedules and crm-web::crm::schedules.

The selected operation can pass through any one of these grants:

- CRM administrators and sales managers.
- Salespeople, when Service Config.Hosting/native mode is not desktop-local.
- The salespeople reached through Crm Account (owns) → 销售 (holds).
- The salespeople reached through 客户 (has) → Crm Account (sales-owns) → 销售 (holds).
- The salespeople reached through 客户 (has) → Crm Account (channel-owns) → 销售 (holds).
- Salespeople, when 客户.Pool state is in.
- The salespeople reached through 桌面设置 (keeps) → Crm Account (uses) → 销售 (holds), when 桌面设置.Current team binding is absent.
