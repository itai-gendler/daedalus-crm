---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "gift-log",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm"
        },
        {
          "place": "crm-desktop::crm"
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

# Only operations staff may read Gift Log

This Rule governs read operations on Gift Log at crm-web::crm and crm-desktop::crm.

The selected operation can pass through any one of these grants:

- Operations staff.
