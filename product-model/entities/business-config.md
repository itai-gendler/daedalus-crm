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

# 业务设置

The book’s selected business template, terminology, display labels, options and pool threshold. Stored customer status values remain fixed.

## Information kept

- **Template** — The General or Trade business template controlling supported fields and signing behavior.
- **Terms** — The configured business wording and trade terms used by the supported inputs.
- **Field labels** — The configured wording for displayed CRM fields.
- **Source/grade/industry options** — The configured choices offered for the corresponding CRM fields.
- **Status display labels** — Configured display wording for fixed stored status values.
- **Currency** — The retained currency; summaries do not combine unlike currencies.
- **Pool threshold** — The configured inactivity threshold for eligible automatic pool release.
- **Initial-template choice** — The once-per-new-book initial choice, distinct from ordinary later business-settings editing.
- **Demo marker** — The time marker retained after sample data has been seeded.
