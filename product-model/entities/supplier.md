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
  "relations": [
    {
      "entity": "order",
      "verb": "supplies",
      "cardinality": "one-to-many"
    }
  ]
}
---

# 供应商

The named supplier identity available to enabled trade registration and lightweight order inputs.

## Information kept

- **Name** — The displayed identity of this subject.
