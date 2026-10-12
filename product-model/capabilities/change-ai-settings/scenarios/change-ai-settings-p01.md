---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes change ai settings for the case “Configure provider/model/credential”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::ai-settings"
        },
        "da": {
          "place": "crm-desktop::crm::ai-settings"
        }
      }
    },
    {
      "text": "Configure provider/model/credential. Configures provider, model, key and recognition. Clearing UI configuration can expose environment fallback. MCP generation/rotation/disabling stays in this settings section and rotation invalidates the prior token.",
      "kind": "product",
      "entities": [
        {
          "entity": "ai-config",
          "effect": "changes",
          "facts": [
            "Provider address",
            "Model",
            "Choices",
            "Credential",
            "Credential hint",
            "Configuration source",
            "Recognition enabled"
          ]
        }
      ],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::ai-settings"
        },
        "da": {
          "place": "crm-desktop::crm::ai-settings"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/SettingsView.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/AiSettingsTab.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/business-config.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/members.ts"
    }
  ]
}
---

# Configure provider/model/credential

## Trigger

The administrator invokes change ai settings for the case “Configure provider/model/credential”.

## Outcome

Configure provider/model/credential. Configures provider, model, key and recognition. Clearing UI configuration can expose environment fallback. MCP generation/rotation/disabling stays in this settings section and rotation invalidates the prior token.
