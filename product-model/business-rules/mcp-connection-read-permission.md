---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mcp-connection",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm"
        },
        {
          "place": "crm-desktop::crm"
        }
      ],
      "facts": [
        "Enabled",
        "Address",
        "Generating member",
        "Generation time"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin"
      ]
    },
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

# Only CRM administrators and CRM administrators, sales managers and salespeople may read Mcp Connection

This Rule governs read operations on Mcp Connection affecting Enabled, Address, Generating member and Generation time at crm-web::crm and crm-desktop::crm.

The selected operation can pass through any one of these grants:

- CRM administrators.
- CRM administrators, sales managers and salespeople.
