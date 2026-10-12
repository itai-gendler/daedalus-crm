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
  ]
}
---

# 操作记录

The visible collective operation history for the CRM book, carrying member, operation, subject, summary, details and time. Recording is best effort.

## Information kept

- **Time** — When the visible log event occurred.
- **Acting member** — The recorded CRM member who performed the audited operation.
- **Operation** — The audited CRM operation's recorded action.
- **Subject** — The arrangement's subject, or the entity and subject identified by an audit record.
- **Summary** — The audit entry's human-readable summary of the recorded operation.
- **Details** — The operation-specific before/after or selected-subject details retained with this audit record.
