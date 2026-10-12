---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "model-usage-log",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::operations::model-usage"
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

# Only operations staff may read Model Usage Log

This Rule governs read operations on Model Usage Log at crm-web::operations::model-usage.

The selected operation can pass through any one of these grants:

- Operations staff.
