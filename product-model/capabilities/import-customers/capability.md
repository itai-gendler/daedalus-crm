---
{
  "availability": [
    {
      "place": "crm-web::crm"
    },
    {
      "place": "crm-desktop::crm"
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

# Import Customers

Reviews the first CSV/XLSX sheet or organized table, up to 10,000 rows and 50 columns. Per-row create/blank-fill/skip results and undo snapshots are retained in one batch; hidden matches are skipped.
