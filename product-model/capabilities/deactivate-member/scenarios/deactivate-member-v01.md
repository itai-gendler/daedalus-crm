---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes deactivate member for the case “Target/recipient/last-admin rejection”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::members"
        }
      }
    },
    {
      "text": "The submitted request reaches this validation boundary: Target/recipient/last-admin rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::members"
        }
      }
    },
    {
      "text": "An unavailable target, identical or inactive recipient, or last-active-administrator violation refuses deactivation and the requested transfer.",
      "kind": "product",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::members"
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

# Target/recipient/last-admin rejection

## Trigger

The administrator invokes deactivate member for the case “Target/recipient/last-admin rejection”.

## Outcome

An unavailable target, identical or inactive recipient, or last-active-administrator violation refuses deactivation and the requested transfer.
