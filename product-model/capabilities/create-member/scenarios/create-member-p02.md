---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes create member for the case “Duplicate-name further confirmation”.",
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
      "text": "Duplicate-name further confirmation. Creates in the deployment’s identity store; duplicate-name creation needs further confirmation. Hosted provisioning does not silently attach an existing cloud account and rolls back applicable failures.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "creates",
          "facts": [
            "Name",
            "Login",
            "Title",
            "Role assignment",
            "Active",
            "Credentials",
            "Favorites",
            "Created time",
            "Last change"
          ],
          "to": "Active"
        },
        {
          "entity": "cloud-account",
          "effect": "reads",
          "facts": [
            "Active",
            "Contact"
          ]
        }
      ],
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

# Duplicate-name further confirmation

## Trigger

The administrator invokes create member for the case “Duplicate-name further confirmation”.

## Outcome

Duplicate-name further confirmation. Creates in the deployment’s identity store; duplicate-name creation needs further confirmation. Hosted provisioning does not silently attach an existing cloud account and rolls back applicable failures.
