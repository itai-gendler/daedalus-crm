---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse subscription for the case “Workspace state/plans/transfer instructions”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::subscription"
        }
      }
    },
    {
      "text": "Workspace state/plans/transfer instructions. Shows the current hosted member’s workspace state, plans and transfer instructions; expired entitlement retains data.",
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
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::subscription"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/billing/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/billing/page.tsx"
    }
  ]
}
---

# Workspace state/plans/transfer instructions

## Trigger

A CRM member invokes browse subscription for the case “Workspace state/plans/transfer instructions”.

## Outcome

Workspace state/plans/transfer instructions. Shows the current hosted member’s workspace state, plans and transfer instructions; expired entitlement retains data.
