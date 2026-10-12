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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/actions.ts"
    }
  ]
}
---

# 系统管理员 / 老板

The fixed ADMIN CRM role; personal information belongs to its CRM account.
