---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes mark won for the case “Win without signing”.",
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
      "text": "Win without signing. General work may win without signing and remain won after signing cancellation/failure. Trade work converts only after its financial registration succeeds; cancel retains the preceding opportunity.",
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
          "to": "WON"
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

# Win without signing

## Trigger

A CRM member invokes mark won for the case “Win without signing”.

## Outcome

Win without signing. General work may win without signing and remain won after signing cancellation/failure. Trade work converts only after its financial registration succeeds; cancel retains the preceding opportunity.
