---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes change business settings for the case “Trade-switch source backfill”.",
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
      "text": "Trade-switch source backfill. Saves business vocabulary and settings under deployment rules. A new database has one initial-template choice. Trade switching backfills actual source details; display labels do not change stored customer statuses.",
      "kind": "product",
      "entities": [
        {
          "entity": "business-config",
          "effect": "changes",
          "facts": [
            "Template",
            "Terms",
            "Field labels",
            "Source/grade/industry options",
            "Status display labels",
            "Currency",
            "Pool threshold",
            "Initial-template choice",
            "Demo marker"
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

# Trade-switch source backfill

## Trigger

The administrator invokes change business settings for the case “Trade-switch source backfill”.

## Outcome

Trade-switch source backfill. Saves business vocabulary and settings under deployment rules. A new database has one initial-template choice. Trade switching backfills actual source details; display labels do not change stored customer statuses.
