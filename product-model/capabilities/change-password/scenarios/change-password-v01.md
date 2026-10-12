---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes change password for the case “Credential/password/shared-account rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Credential/password/shared-account rejection.",
      "kind": "condition",
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
      "text": "Incorrect old credentials, unacceptable new password, invalid desktop code or a shared-account restriction prevents password replacement.",
      "kind": "product",
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

# Credential/password/shared-account rejection

## Trigger

A CRM member invokes change password for the case “Credential/password/shared-account rejection”.

## Outcome

Incorrect old credentials, unacceptable new password, invalid desktop code or a shared-account restriction prevents password replacement.
