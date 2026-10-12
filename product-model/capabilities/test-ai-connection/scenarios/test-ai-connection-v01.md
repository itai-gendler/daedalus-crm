---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes test ai connection for the case “Management/input/unsafe saved-key destination refusal”.",
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
      "text": "The submitted request reaches this validation boundary: Management/input/unsafe saved-key destination refusal.",
      "kind": "condition",
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
      "text": "Failed management/input validation or unsafe saved-key destination resolution refuses the connection test. A saved credential is not sent to a newly supplied unmatched provider address.",
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

# Management/input/unsafe saved-key destination refusal

## Trigger

The administrator invokes test ai connection for the case “Management/input/unsafe saved-key destination refusal”.

## Outcome

Failed management/input validation or unsafe saved-key destination resolution refuses the connection test. A saved credential is not sent to a newly supplied unmatched provider address.
