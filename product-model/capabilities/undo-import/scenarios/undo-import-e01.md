---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes undo import for the case “Later changes/dependencies cause partial retention”.",
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
      "text": "Later changes, dependent records and the auxiliary trade fingerprint gap can retain some imported data; the batch records the partial undo.",
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

# Later changes/dependencies cause partial retention

## Trigger

A CRM member invokes undo import for the case “Later changes/dependencies cause partial retention”.

## Outcome

Later changes, dependent records and the auxiliary trade fingerprint gap can retain some imported data; the batch records the partial undo.
