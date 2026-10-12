---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "sync-team",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::operations"
        }
      ],
      "facts": [
        "Active",
        "Activation time"
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
      "target": "src/lib/sync/tables.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/gateway-auth.ts"
    }
  ]
}
---

# Only operations staff may change 同步团队

This Rule governs change operations on 同步团队 affecting Active and Activation time at crm-web::operations.

The selected operation can pass through any one of these grants:

- Operations staff.
