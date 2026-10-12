---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes mark lost for the case “Confirm loss”.",
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
      "text": "Confirm loss. Confirmed loss records LOST, closure time and the applicable stage/probability. Undo can use the prior values; no independent Lost reason fact is kept.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "changes",
          "facts": [
            "Stage",
            "Probability",
            "Status",
            "Closed time",
            "Last change"
          ],
          "from": "OPEN",
          "to": "LOST"
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

# Confirm loss

## Trigger

A CRM member invokes mark lost for the case “Confirm loss”.

## Outcome

Confirm loss. Confirmed loss records LOST, closure time and the applicable stage/probability. Undo can use the prior values; no independent Lost reason fact is kept.
