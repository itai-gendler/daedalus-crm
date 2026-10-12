---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "lead",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::customers"
        },
        {
          "place": "crm-desktop::crm::leads"
        },
        {
          "place": "crm-web::crm::customers"
        },
        {
          "place": "crm-web::crm::leads"
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
          "verb": "responsible-for",
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
          "verb": "converted-to",
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
    },
    {
      "related": [
        {
          "verb": "converted-to",
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

# Only CRM administrators and sales managers, salespeople and related salespeople may change 线索

This Rule governs change operations on 线索 at crm-desktop::crm::customers, crm-desktop::crm::leads, crm-web::crm::customers and crm-web::crm::leads.

The selected operation can pass through any one of these grants:

- CRM administrators and sales managers.
- Salespeople, when Service Config.Hosting/native mode is not desktop-local.
- The salespeople reached through Crm Account (responsible-for) → 销售 (holds).
- The salespeople reached through 客户 (converted-to) → Crm Account (sales-owns) → 销售 (holds).
- The salespeople reached through 桌面设置 (keeps) → Crm Account (uses) → 销售 (holds), when 桌面设置.Current team binding is absent.
- The salespeople reached through 客户 (converted-to) → Crm Account (channel-owns) → 销售 (holds).
- Salespeople, when 客户.Pool state is in.
