---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse members for the case “Roster and work counts”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::members"
        }
      }
    },
    {
      "text": "Roster and work counts. Shows roster and work counts, retaining inactive members in the available management context.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "reads",
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
          ]
        }
      ],
      "actor": "crm-sales",
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

# Roster and work counts

## Trigger

A CRM member invokes browse members for the case “Roster and work counts”.

## Outcome

Roster and work counts. Shows roster and work counts, retaining inactive members in the available management context.
