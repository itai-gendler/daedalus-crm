---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes convert lead for the case “Duplicate, hidden-owner hint, or concurrent conversion”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::leads"
        },
        "da": {
          "place": "crm-desktop::crm::leads"
        }
      }
    },
    {
      "text": "A duplicate normalized phone or trade email prevents a second customer. A visible duplicate returns its customer identity and merge route; a hidden duplicate returns the responsible colleague hint while withholding customer name and ID. Concurrent conversion is gated: the later request reports that the lead has just been converted and creates no additional customer.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::leads"
        },
        "da": {
          "place": "crm-desktop::crm::leads"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/leads/actions.ts"
    }
  ]
}
---

# Duplicate, hidden-owner hint, or concurrent conversion

## Trigger

A CRM member invokes convert lead for the case “Duplicate, hidden-owner hint, or concurrent conversion”.

## Outcome

A duplicate normalized phone or trade email prevents a second customer. A visible duplicate returns its customer identity and merge route; a hidden duplicate returns the responsible colleague hint while withholding customer name and ID. Concurrent conversion is gated: the later request reports that the lead has just been converted and creates no additional customer.
