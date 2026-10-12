---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes enable channel for the case “Enable”.",
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
      "text": "Enable. Marks the selected channel active.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "changes",
          "facts": [
            "Active",
            "Last change"
          ],
          "from": "Inactive",
          "to": "Active"
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

# Enable

## Trigger

A CRM member invokes enable channel for the case “Enable”.

## Outcome

Enable. Marks the selected channel active.
