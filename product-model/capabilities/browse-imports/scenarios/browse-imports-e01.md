---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse imports for the case “Read failure distinguished from empty history”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::import-history"
        },
        "da": {
          "place": "crm-desktop::crm::import-history"
        }
      }
    },
    {
      "text": "Read failure is presented as failure, rather than converted to empty history.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::import-history"
        },
        "da": {
          "place": "crm-desktop::crm::import-history"
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

# Read failure distinguished from empty history

## Trigger

A CRM member invokes browse imports for the case “Read failure distinguished from empty history”.

## Outcome

Read failure is presented as failure, rather than converted to empty history.
