---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes change ai settings for the case “Generate/rotate/disable MCP”.",
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
      "text": "Generate/rotate/disable MCP. Configures provider, model, key and recognition. Clearing UI configuration can expose environment fallback. MCP generation/rotation/disabling stays in this settings section and rotation invalidates the prior token.",
      "kind": "product",
      "entities": [
        {
          "entity": "mcp-connection",
          "effect": "changes",
          "facts": [
            "Enabled",
            "Address",
            "Credential",
            "Generating member",
            "Generation time"
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

# Generate/rotate/disable MCP

## Trigger

The administrator invokes change ai settings for the case “Generate/rotate/disable MCP”.

## Outcome

Generate/rotate/disable MCP. Configures provider, model, key and recognition. Clearing UI configuration can expose environment fallback. MCP generation/rotation/disabling stays in this settings section and rotation invalidates the prior token.
