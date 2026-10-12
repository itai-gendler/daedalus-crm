---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-ops-overview"
    },
    {
      "type": "capability",
      "id": "browse-cloud-accounts"
    },
    {
      "type": "capability",
      "id": "browse-model-usage"
    },
    {
      "type": "entity",
      "id": "cloud-account"
    },
    {
      "type": "entity",
      "id": "model-usage-log"
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

# Operations statistics retain their actual test-account exclusions

Operations summaries exclude test accounts where implemented and retain the detailed account history. Configured operations identities remain inherently test. Monetary cost requires configured prices and available recorded token usage; monthly CRM feature counts are separate audit-derived data.
