---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes deactivate member for the case “Identity-store/transaction failure”.",
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
      "text": "The local transfer and inactive flag share a transaction. A local failure does not report deactivation success; a later hosted-membership failure can occur after the local transaction, so future work and the inactive flag may already have changed.",
      "kind": "product",
      "entities": [],
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

# Identity-store/transaction failure

## Trigger

The administrator invokes deactivate member for the case “Identity-store/transaction failure”.

## Outcome

The local transfer and inactive flag share a transaction. A local failure does not report deactivation success; a later hosted-membership failure can occur after the local transaction, so future work and the inactive flag may already have changed.
