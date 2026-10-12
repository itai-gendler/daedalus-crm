---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes attach contact for the case “Associate new customer”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::contacts"
        },
        "da": {
          "place": "crm-desktop::crm::contacts"
        }
      }
    },
    {
      "text": "Associate new customer. Associates an unassigned contact with the selected customer. Former-customer restoration repairs only eligible null communication links; a different customer receives no former links.",
      "kind": "product",
      "entities": [
        {
          "entity": "unassigned-contact",
          "effect": "removes",
          "from": "Unassigned"
        },
        {
          "entity": "assigned-contact",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "WeChat",
            "Email",
            "Position",
            "Notes",
            "Primary",
            "Created time",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::contacts"
        },
        "da": {
          "place": "crm-desktop::crm::contacts"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#saveUnassignedContact"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#undoDetachContact"
    }
  ]
}
---

# Associate new customer

## Trigger

A CRM member invokes attach contact for the case “Associate new customer”.

## Outcome

Associate new customer. Associates an unassigned contact with the selected customer. Former-customer restoration repairs only eligible null communication links; a different customer receives no former links.
