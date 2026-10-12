---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes export customers for the case “Independent export limits”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      }
    },
    {
      "text": "The export uses the current filters across pages, capped independently at 20,000 customers and 50,000 follow-ups. The two truncation flags describe their respective limits; only follow-ups belonging to exported customers enter the second sheet, with shared-demo phone masking preserved.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/import-actions.ts"
    }
  ]
}
---

# Independent export limits

## Trigger

A CRM member invokes export customers for the case “Independent export limits”.

## Outcome

The export uses the current filters across pages, capped independently at 20,000 customers and 50,000 follow-ups. The two truncation flags describe their respective limits; only follow-ups belonging to exported customers enter the second sheet, with shared-demo phone masking preserved.
