---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "desktop-config",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::public::server-connection"
        }
      ],
      "facts": [
        "Data mode"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor",
        "crm-admin",
        "crm-manager",
        "crm-sales"
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

# Only visitors, CRM administrators, sales managers and salespeople may change 桌面设置

This Rule governs change operations on 桌面设置 affecting Data mode at crm-desktop::public::server-connection.

The selected operation can pass through any one of these grants:

- Visitors, CRM administrators, sales managers and salespeople.
