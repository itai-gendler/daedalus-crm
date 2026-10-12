---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes mark won for the case “Enter signing/order registration”.",
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
      "text": "Enter signing/order registration. General work may win without signing and remain won after signing cancellation/failure. Trade work converts only after its financial registration succeeds; cancel retains the preceding opportunity.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "reads",
          "facts": [
            "Name",
            "Amount",
            "Currency",
            "Stage",
            "Probability",
            "Status"
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

# Enter signing/order registration

## Trigger

A CRM member invokes mark won for the case “Enter signing/order registration”.

## Outcome

Enter signing/order registration. General work may win without signing and remain won after signing cancellation/failure. Trade work converts only after its financial registration succeeds; cancel retains the preceding opportunity.
