---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "desktop-config",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm"
        },
        {
          "place": "crm-desktop::operations"
        },
        {
          "place": "crm-web::public::login"
        },
        {
          "place": "crm-desktop::public::login-or-registration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin",
        "crm-manager",
        "crm-sales"
      ]
    },
    {
      "unattended": true
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

# Only CRM administrators, sales managers and salespeople and the Product's scheduled process may change 桌面设置

This Rule governs change operations on 桌面设置 at crm-desktop::crm, crm-desktop::operations, crm-web::public::login and crm-desktop::public::login-or-registration.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
- The Product's scheduled process.
