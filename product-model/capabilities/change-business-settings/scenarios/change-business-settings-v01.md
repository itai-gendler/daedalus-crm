---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes change business settings for the case “Role/shared/invalid configuration”.",
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
      "text": "The submitted request reaches this validation boundary: Role/shared/invalid configuration.",
      "kind": "condition",
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
      "text": "A failed configuration-management check, shared-workspace restriction or invalid configuration refuses saving; the rejected template/options are not reported active.",
      "kind": "product",
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

# Role/shared/invalid configuration

## Trigger

The administrator invokes change business settings for the case “Role/shared/invalid configuration”.

## Outcome

A failed configuration-management check, shared-workspace restriction or invalid configuration refuses saving; the rejected template/options are not reported active.
