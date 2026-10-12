---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes disable channel for the case “Disable”.",
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
      "text": "Disable. Marks the selected channel inactive without deleting attribution.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "changes",
          "facts": [
            "Active",
            "Last change"
          ],
          "from": "Active",
          "to": "Inactive"
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

# Disable

## Trigger

A CRM member invokes disable channel for the case “Disable”.

## Outcome

Disable. Marks the selected channel inactive without deleting attribution.
