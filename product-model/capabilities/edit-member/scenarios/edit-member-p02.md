---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes edit member for the case “Reset in correct identity store”.",
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
      "text": "Reset in correct identity store. Edits role/profile or resets credentials in the correct identity store, with last-admin and duplicate-name safeguards.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "changes",
          "facts": [
            "Name",
            "Login",
            "Title",
            "Role assignment",
            "Active",
            "Credentials",
            "Last change"
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

# Reset in correct identity store

## Trigger

The administrator invokes edit member for the case “Reset in correct identity store”.

## Outcome

Reset in correct identity store. Edits role/profile or resets credentials in the correct identity store, with last-admin and duplicate-name safeguards.
