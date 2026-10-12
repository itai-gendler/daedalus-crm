---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit channel for the case “Ordinary edit”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::channels"
        },
        "da": {
          "place": "crm-desktop::crm::channels"
        }
      }
    },
    {
      "text": "Ordinary edit. Uses the channel version guard and validates unique name and eligible owner; existing historical customer attribution is not automatically rewritten.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "changes",
          "facts": [
            "Name",
            "Phone",
            "Notes",
            "Owner",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::channels"
        },
        "da": {
          "place": "crm-desktop::crm::channels"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/channels/actions.ts"
    }
  ]
}
---

# Ordinary edit

## Trigger

A CRM member invokes edit channel for the case “Ordinary edit”.

## Outcome

Ordinary edit. Uses the channel version guard and validates unique name and eligible owner; existing historical customer attribution is not automatically rewritten.
