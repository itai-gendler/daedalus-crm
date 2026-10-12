---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    }
  ],
  "domain": "import-history"
}
---

# 导入批次

An addressable import execution containing row results and creation/fill snapshots used for its once-only eligible undo.

## Information kept

- **File name** — The name of the imported file or reviewed table source.
- **Importer** — The CRM account that executed the batch.
- **Import time** — When this batch executed its import.
- **Results** — The batch's created, filled, skipped and failed row outcomes.
- **Creation snapshots** — The created customers and associated input values retained for eligible import undo.
- **Fill snapshots** — The prior and filled values retained to restore still-matching imported fills.
- **Undo result** — The retained import-undo outcome, including partial restoration or retained rows.
- **Undone time** — When this batch was marked undone.

## States

### Recorded

The batch retains its executed row results and has not yet been marked undone.

### Undone

The batch has recorded its undo result and time, including any retained rows.
