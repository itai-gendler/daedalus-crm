---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "workspace",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::operations"
        }
      ],
      "facts": [
        "Status",
        "Trial expiry",
        "Paid expiry"
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

# Only operations staff may change 工作区

This Rule governs change operations on 工作区 affecting Status, Trial expiry and Paid expiry at crm-web::operations.

The selected operation can pass through any one of these grants:

- Operations staff.
