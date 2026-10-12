---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "audit-log",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-web::crm::business-settings"
        },
        {
          "place": "crm-desktop::crm::business-settings"
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
          "verb": "authored",
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

# Only CRM administrators and sales managers, salespeople and related salespeople may remove 操作记录

This Rule governs remove operations on 操作记录 at crm-web::crm::business-settings and crm-desktop::crm::business-settings.

The selected operation can pass through any one of these grants:

- CRM administrators and sales managers.
- Salespeople, when Service Config.Hosting/native mode is not desktop-local.
- The salespeople reached through Crm Account (authored) → 销售 (holds).
- The salespeople reached through 桌面设置 (keeps) → Crm Account (uses) → 销售 (holds), when 桌面设置.Current team binding is absent.
