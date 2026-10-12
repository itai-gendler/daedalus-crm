---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes read shortcuts for the case “Session rejection”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::shortcuts"
        },
        "da": {
          "place": "crm-desktop::crm::shortcuts"
        }
      }
    },
    {
      "text": "The submitted request reaches this validation boundary: Session rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::shortcuts"
        },
        "da": {
          "place": "crm-desktop::crm::shortcuts"
        }
      }
    },
    {
      "text": "The session rejection prevents the requested CRM operation from completing and is exposed through its existing login/error process.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::shortcuts"
        },
        "da": {
          "place": "crm-desktop::crm::shortcuts"
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

# Session rejection

## Trigger

A CRM member invokes read shortcuts for the case “Session rejection”.

## Outcome

The session rejection prevents the requested CRM operation from completing and is exposed through its existing login/error process.
