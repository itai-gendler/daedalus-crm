---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes create channel for the case “Create”.",
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
      "text": "Create. Creates a validated unique named channel with an eligible owner.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "Notes",
            "Owner",
            "Active",
            "Created time",
            "Last change"
          ],
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

# Create

## Trigger

A CRM member invokes create channel for the case “Create”.

## Outcome

Create. Creates a validated unique named channel with an eligible owner.
