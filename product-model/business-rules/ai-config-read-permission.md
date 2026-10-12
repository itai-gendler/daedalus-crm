---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "ai-config",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-desktop::crm::ai-settings"
        },
        {
          "place": "crm-desktop::crm::customer-import"
        },
        {
          "place": "crm-web::crm::ai-settings"
        },
        {
          "place": "crm-web::crm::customer-import"
        }
      ],
      "facts": [
        "Provider address",
        "Model",
        "Choices",
        "Credential hint",
        "Configuration source",
        "Recognition enabled"
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

# Only CRM administrators and CRM administrators, sales managers and salespeople may read AI设置

This Rule governs read operations on AI设置 affecting Provider address, Model, Choices, Credential hint, Configuration source and Recognition enabled at crm-desktop::crm::ai-settings, crm-desktop::crm::customer-import, crm-web::crm::ai-settings and crm-web::crm::customer-import.

The selected operation can pass through any one of these grants:

- CRM administrators.
- CRM administrators, sales managers and salespeople.
