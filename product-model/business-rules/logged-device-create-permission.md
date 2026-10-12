---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "logged-device",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::public::login"
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

# Only CRM administrators, sales managers and salespeople may create 登录设备

This Rule governs create operations on 登录设备 at crm-web::public::login.

The selected operation can pass through any one of these grants:

- CRM administrators, sales managers and salespeople.
