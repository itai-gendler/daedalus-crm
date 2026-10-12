---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes reactivate member for the case “Restore user and hosted membership”.",
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
      "text": "Restore user and hosted membership. Restores the CRM user and applicable hosted membership without inventing cloud deactivation lifecycle.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "changes",
          "facts": [
            "Active",
            "Last change"
          ],
          "from": "Inactive",
          "to": "Active"
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

# Restore user and hosted membership

## Trigger

The administrator invokes reactivate member for the case “Restore user and hosted membership”.

## Outcome

Restore user and hosted membership. Restores the CRM user and applicable hosted membership without inventing cloud deactivation lifecycle.
