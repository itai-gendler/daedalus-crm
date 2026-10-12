---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse devices for the case “Empty/older client missing descriptors”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::password"
        }
      }
    },
    {
      "text": "No matching records produce an empty result. A bounded result retains its limit and does not claim the omitted records are absent.",
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
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::password"
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

# Empty/older client missing descriptors

## Trigger

A CRM member invokes browse devices for the case “Empty/older client missing descriptors”.

## Outcome

No matching records produce an empty result. A bounded result retains its limit and does not claim the omitted records are absent.
