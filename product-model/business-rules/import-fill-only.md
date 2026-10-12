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

# Import fills eligible blanks without rewriting existing identity or attribution

Matching uses the established phone/email path and skips inaccessible matches. Eligible existing records receive blank-field fills; existing identity, status and attribution are preserved. Unsupported/unknown columns can contribute notes under the implemented mapping rather than becoming invented managed fields.
