---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes reactivate member for the case “Missing cloud dependency”.",
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
      "text": "The local member is set active first. In hosted mode a missing current tenant or account link skips membership restoration while the local reactivation can still succeed; an attempted membership restoration failure can occur after this local change. No missing-cloud-dependency refusal is invented.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "changes",
          "facts": [
            "Active"
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

# Missing cloud dependency

## Trigger

The administrator invokes reactivate member for the case “Missing cloud dependency”.

## Outcome

The local member is set active first. In hosted mode a missing current tenant or account link skips membership restoration while the local reactivation can still succeed; an attempted membership restoration failure can occur after this local change. No missing-cloud-dependency refusal is invented.
