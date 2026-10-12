---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse imports for the case “Recent batches”.",
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
      "text": "Recent batches. Shows recent batches; a read failure is reported separately from genuinely empty import history.",
      "kind": "product",
      "entities": [
        {
          "entity": "import-batch",
          "effect": "reads",
          "facts": [
            "File name",
            "Importer",
            "Import time",
            "Results",
            "Creation snapshots",
            "Fill snapshots",
            "Undo result",
            "Undone time"
          ]
        }
      ],
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

# Recent batches

## Trigger

A CRM member invokes browse imports for the case “Recent batches”.

## Outcome

Recent batches. Shows recent batches; a read failure is reported separately from genuinely empty import history.
