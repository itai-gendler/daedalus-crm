---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse devices for the case “Own valid desktop devices”.",
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
      "text": "Own valid desktop devices. Reads the current cloud account’s valid desktop devices; older clients may lack descriptors and some deployment identity stores offer no device list.",
      "kind": "product",
      "entities": [
        {
          "entity": "logged-device",
          "effect": "reads",
          "facts": [
            "Name",
            "Platform",
            "Architecture",
            "Client version",
            "Login time",
            "Last use",
            "Revocation"
          ]
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

# Own valid desktop devices

## Trigger

A CRM member invokes browse devices for the case “Own valid desktop devices”.

## Outcome

Own valid desktop devices. Reads the current cloud account’s valid desktop devices; older clients may lack descriptors and some deployment identity stores offer no device list.
