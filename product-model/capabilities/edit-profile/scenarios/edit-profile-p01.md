---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit profile for the case “Own name/title”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::profile"
        },
        "da": {
          "place": "crm-desktop::crm::profile"
        }
      }
    },
    {
      "text": "Own name/title. Edits only the current personal account’s name/title under shared-account restrictions.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "changes",
          "facts": [
            "Name",
            "Title",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::profile"
        },
        "da": {
          "place": "crm-desktop::crm::profile"
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

# Own name/title

## Trigger

A CRM member invokes edit profile for the case “Own name/title”.

## Outcome

Own name/title. Edits only the current personal account’s name/title under shared-account restrictions.
