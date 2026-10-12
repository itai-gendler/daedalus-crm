---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "organize-pasted-list"
    },
    {
      "type": "capability",
      "id": "recognize-import-columns"
    },
    {
      "type": "capability",
      "id": "import-customers"
    },
    {
      "type": "entity",
      "id": "ai-config"
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
      "target": "src/app/(app)/dashboard/apply.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/credits.ts"
    }
  ]
}
---

# AI import preparation uses source-supported values and preserves manual review

Organizing pasted text produces a reviewable table using source-supported people and values. Optional column judgment sends headers and the first three rows. Failed or late recognition preserves manual mapping and a changed preview; neither preparation process imports customers before human review.
