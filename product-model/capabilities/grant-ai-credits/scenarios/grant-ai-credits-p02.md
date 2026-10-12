---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes grant ai credits for the case “Workspace grant”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::account-record"
        }
      }
    },
    {
      "text": "Workspace grant. Grants normalized credits to the chosen account or workspace. Account grants have visible gift history; no separate visible workspace-ledger entity is inferred.",
      "kind": "product",
      "entities": [
        {
          "entity": "workspace",
          "effect": "changes",
          "facts": [
            "AI allowance"
          ]
        }
      ],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::account-record"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/data.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/guard.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ops-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/ops-notices.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/feedback-reply.ts"
    }
  ]
}
---

# Workspace grant

## Trigger

The operator invokes grant ai credits for the case “Workspace grant”.

## Outcome

Workspace grant. Grants normalized credits to the chosen account or workspace. Account grants have visible gift history; no separate visible workspace-ledger entity is inferred.
