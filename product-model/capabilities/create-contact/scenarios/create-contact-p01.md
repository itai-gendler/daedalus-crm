---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes create contact for the case “Customer contact with primary-contact handling”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-record"
        },
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      }
    },
    {
      "text": "Customer contact with primary-contact handling. Creates a customer contact; selecting Primary transactionally clears any previous primary so there is at most one.",
      "kind": "product",
      "entities": [
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
          "place": "crm-web::crm::customer-record"
        },
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#saveContact"
    }
  ]
}
---

# Customer contact with primary-contact handling

## Trigger

A CRM member invokes create contact for the case “Customer contact with primary-contact handling”.

## Outcome

Customer contact with primary-contact handling. Creates a customer contact; selecting Primary transactionally clears any previous primary so there is at most one.
