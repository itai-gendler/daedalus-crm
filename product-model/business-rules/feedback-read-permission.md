---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "feedback",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::operations::feedback"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "operator"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/mcp/tools.ts"
    }
  ]
}
---

# Only operations staff may read 反馈

This Rule governs read operations on 反馈 at crm-web::operations::feedback.

The selected operation can pass through any one of these grants:

- Operations staff.
