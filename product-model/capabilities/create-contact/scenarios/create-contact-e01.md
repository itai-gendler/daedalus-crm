---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes create contact for the case “Customer disappears/save fails”.",
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
      "text": "If the selected customer disappears or the contact save fails, no successful contact creation is reported. Primary-contact changes and the contact save use their transactional boundary rather than leaving a new successful contact attached to a missing customer.",
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

# Customer disappears/save fails

## Trigger

A CRM member invokes create contact for the case “Customer disappears/save fails”.

## Outcome

If the selected customer disappears or the contact save fails, no successful contact creation is reported. Primary-contact changes and the contact save use their transactional boundary rather than leaving a new successful contact attached to a missing customer.
