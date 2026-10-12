---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes browse workspaces for the case “Membership/expiry/allowance/notes”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::workspaces"
        }
      }
    },
    {
      "text": "Membership/expiry/allowance/notes. Shows at most 200 workspaces with membership, dates, allowance and notes.",
      "kind": "product",
      "entities": [
        {
          "entity": "workspace",
          "effect": "reads",
          "facts": [
            "Name",
            "Address/slug",
            "Status",
            "Trial expiry",
            "Paid expiry",
            "Plan",
            "AI allowance",
            "Notes",
            "Payment references"
          ]
        }
      ],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::workspaces"
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

# Membership/expiry/allowance/notes

## Trigger

The operator invokes browse workspaces for the case “Membership/expiry/allowance/notes”.

## Outcome

Membership/expiry/allowance/notes. Shows at most 200 workspaces with membership, dates, allowance and notes.
