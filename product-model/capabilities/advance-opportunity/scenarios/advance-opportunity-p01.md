---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes advance opportunity for the case “Advance/restore stage”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::opportunities"
        },
        "da": {
          "place": "crm-desktop::crm::opportunities"
        }
      }
    },
    {
      "text": "Advance/restore stage. Stage movement is distinct from guarded status normalization and can leave OPEN at the winning stage. Entering the winning stage opens the template-specific financial process.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "changes",
          "facts": [
            "Stage",
            "Probability",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::opportunities"
        },
        "da": {
          "place": "crm-desktop::crm::opportunities"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/opportunities/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-contract.ts"
    }
  ]
}
---

# Advance/restore stage

## Trigger

A CRM member invokes advance opportunity for the case “Advance/restore stage”.

## Outcome

Advance/restore stage. Stage movement is distinct from guarded status normalization and can leave OPEN at the winning stage. Entering the winning stage opens the template-specific financial process.
