---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "service-config",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-desktop::operations"
        },
        {
          "place": "crm-web::operations"
        },
        {
          "place": "model-gateway"
        }
      ],
      "facts": [
        "Hosting/native mode",
        "Shared workspace address",
        "Registration policy/redirect",
        "Verification policy",
        "Generation model choices"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor",
        "crm-admin",
        "crm-manager",
        "crm-sales",
        "operator",
        "model-client"
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

# Only visitors, CRM administrators, sales managers, salespeople, operations staff and model clients may read Service Config

This Rule governs read operations on Service Config affecting Hosting/native mode, Shared workspace address, Registration policy/redirect, Verification policy and Generation model choices at crm-desktop::operations, crm-web::operations and model-gateway.

The selected operation can pass through any one of these grants:

- Visitors, CRM administrators, sales managers, salespeople, operations staff and model clients.
