---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes change business settings for the case “New-database initial template”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::business-settings"
        },
        "da": {
          "place": "crm-desktop::crm::business-settings"
        }
      }
    },
    {
      "text": "New-database initial template. Saves business vocabulary and settings under deployment rules. A new database has one initial-template choice. Trade switching backfills actual source details; display labels do not change stored customer statuses.",
      "kind": "product",
      "entities": [
        {
          "entity": "business-config",
          "effect": "changes",
          "facts": [
            "Template",
            "Initial-template choice",
            "Terms",
            "Field labels",
            "Source/grade/industry options",
            "Status display labels",
            "Currency"
          ]
        }
      ],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::business-settings"
        },
        "da": {
          "place": "crm-desktop::crm::business-settings"
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

# New-database initial template

## Trigger

The administrator invokes change business settings for the case “New-database initial template”.

## Outcome

New-database initial template. Saves business vocabulary and settings under deployment rules. A new database has one initial-template choice. Trade switching backfills actual source details; display labels do not change stored customer statuses.
