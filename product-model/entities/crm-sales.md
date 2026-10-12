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

# 销售

The fixed SALES CRM role; native team record work uses the implemented ownership scope.
