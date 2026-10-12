---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes import customers for the case “File-table import”.",
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
      "text": "File-table import. Reviews the first CSV/XLSX sheet or organized table, up to 10,000 rows and 50 columns. Per-row create/blank-fill/skip results and undo snapshots are retained in one batch; hidden matches are skipped.",
      "kind": "product",
      "entities": [
        {
          "entity": "import-batch",
          "effect": "creates",
          "facts": [
            "File name",
            "Importer",
            "Import time",
            "Results",
            "Creation snapshots",
            "Fill snapshots",
            "Undo result",
            "Undone time"
          ],
          "to": "Recorded"
        }
      ],
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
      "text": "The eligible row is created in the selected customer scope.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "creates",
          "facts": [
            "Name",
            "Phone",
            "WhatsApp",
            "WeChat",
            "Country",
            "Email",
            "School/company",
            "Grade",
            "Major",
            "Follow-up status",
            "Decision status",
            "Expected signing date",
            "Sales owner",
            "Direct source",
            "Direct channel",
            "Referrer",
            "Attributed channel",
            "Attributed customer",
            "Channel owner",
            "Notes",
            "Latest follow-up",
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by",
            "Created time",
            "Last change"
          ]
        }
      ],
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

# File-table import

## Trigger

A CRM member invokes import customers for the case “File-table import”.

## Outcome

File-table import. Reviews the first CSV/XLSX sheet or organized table, up to 10,000 rows and 50 columns. Per-row create/blank-fill/skip results and undo snapshots are retained in one batch; hidden matches are skipped.
