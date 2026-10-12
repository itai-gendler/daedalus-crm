---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "cloud-account",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::operations"
        }
      ],
      "facts": [
        "Test marker",
        "Test history"
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

# Only operations staff may change Cloud Account

This Rule governs change operations on Cloud Account affecting Test marker and Test history at crm-web::operations.

The selected operation can pass through any one of these grants:

- Operations staff.
