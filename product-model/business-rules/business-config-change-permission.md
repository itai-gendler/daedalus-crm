---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "business-config",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::business-settings"
        },
        {
          "place": "crm-web::crm::business-settings"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin"
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

# Only CRM administrators may change 业务设置

This Rule governs change operations on 业务设置 at crm-desktop::crm::business-settings and crm-web::crm::business-settings.

The selected operation can pass through any one of these grants:

- CRM administrators.
