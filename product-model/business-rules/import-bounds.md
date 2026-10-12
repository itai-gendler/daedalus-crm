---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "import-customers"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "import-batch"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
    }
  ]
}
---

# Customer import uses one reviewed sheet within row and column bounds

CSV/XLSX import uses the supported first sheet, with at most 10,000 rows and 50 columns. The person reviews mappings and eligible rows. Execution records per-row created, filled, skipped and failed outcomes, including partial completion.
