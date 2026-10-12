---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes revoke device for the case “Revoke selected own device”.",
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
      "text": "Revoke selected own device. Revokes only the selected device of the current cloud account. An offline client exits on its later check; local files remain.",
      "kind": "product",
      "entities": [
        {
          "entity": "logged-device",
          "effect": "changes",
          "facts": [
            "Revocation"
          ],
          "from": "Active",
          "to": "Revoked"
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

# Revoke selected own device

## Trigger

A CRM member invokes revoke device for the case “Revoke selected own device”.

## Outcome

Revoke selected own device. Revokes only the selected device of the current cloud account. An offline client exits on its later check; local files remain.
