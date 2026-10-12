---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes organize pasted list for the case “No source-supported people/model failure”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-import"
        },
        "da": {
          "place": "crm-desktop::crm::customer-import"
        }
      }
    },
    {
      "text": "The provider or model failure is shown; generated text or proposals are not treated as a confirmed CRM write.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-import"
        },
        "da": {
          "place": "crm-desktop::crm::customer-import"
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

# No source-supported people/model failure

## Trigger

A CRM member invokes organize pasted list for the case “No source-supported people/model failure”.

## Outcome

The provider or model failure is shown; generated text or proposals are not treated as a confirmed CRM write.
