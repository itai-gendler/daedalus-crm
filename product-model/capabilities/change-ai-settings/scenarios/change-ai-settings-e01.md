---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes change ai settings for the case “Environment fallback/old token invalidation”.",
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
      "text": "Clearing UI provider settings allows the applicable environment/cloud provider configuration to become effective again. Generating or rotating the MCP token invalidates the old token, and disabling it prevents later use; clearing provider settings does not mean environment credentials were deleted.",
      "kind": "product",
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

# Environment fallback/old token invalidation

## Trigger

The administrator invokes change ai settings for the case “Environment fallback/old token invalidation”.

## Outcome

Clearing UI provider settings allows the applicable environment/cloud provider configuration to become effective again. Generating or rotating the MCP token invalidates the old token, and disabling it prevents later use; clearing provider settings does not mean environment credentials were deleted.
