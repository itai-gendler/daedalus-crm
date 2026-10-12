---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes create contact for the case “Invalid input/customer”.",
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
      "text": "The submitted request reaches this validation boundary: Invalid input/customer.",
      "kind": "condition",
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
      "text": "Invalid contact input or an unavailable customer prevents creation; the contact is not attached to an arbitrary replacement customer.",
      "kind": "product",
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

# Invalid input/customer

## Trigger

A CRM member invokes create contact for the case “Invalid input/customer”.

## Outcome

Invalid contact input or an unavailable customer prevents creation; the contact is not attached to an arbitrary replacement customer.
