---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes create member for the case “Cloud provisioning failure/rollback”.",
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
      "text": "Hosted creation first makes a managed CRM identity, then provisions its cloud account/membership. If provisioning fails, the action attempts to delete the new CRM identity and returns the provisioning error; best-effort deletion does not establish a universal rollback guarantee.",
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

# Cloud provisioning failure/rollback

## Trigger

The administrator invokes create member for the case “Cloud provisioning failure/rollback”.

## Outcome

Hosted creation first makes a managed CRM identity, then provisions its cloud account/membership. If provisioning fails, the action attempts to delete the new CRM identity and returns the provisioning error; best-effort deletion does not establish a universal rollback guarantee.
