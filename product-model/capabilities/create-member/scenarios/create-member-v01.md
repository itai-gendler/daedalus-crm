---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes create member for the case “Role/credential/duplicate rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Role/credential/duplicate rejection.",
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
      "text": "Invalid role or credentials, duplicate login or unconfirmed duplicate-name information prevents the requested new member from being reported created.",
      "kind": "product",
      "entities": [
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

# Role/credential/duplicate rejection

## Trigger

The administrator invokes create member for the case “Role/credential/duplicate rejection”.

## Outcome

Invalid role or credentials, duplicate login or unconfirmed duplicate-name information prevents the requested new member from being reported created.
