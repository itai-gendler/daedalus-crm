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

# Recognize Import Columns

Opt-in unresolved-column judgment sends headers and first three rows to the judgment model. It consumes no generative credit; late/failing results preserve manual mappings and preview.
