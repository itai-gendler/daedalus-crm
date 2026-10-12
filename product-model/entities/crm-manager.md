---
{
  "acts": "external",
  "kind": "person",
  "relations": [
    {
      "entity": "crm-account",
      "verb": "holds",
      "cardinality": "one-to-one"
    },
    {
      "entity": "ai-agent",
      "verb": "connects",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    }
  ]
}
---

# 销售主管

The fixed MANAGER CRM role. Workspace administration is distinct from product operations.
