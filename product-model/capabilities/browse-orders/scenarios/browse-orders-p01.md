---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse orders for the case “Lightweight list”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::orders"
        },
        "da": {
          "place": "crm-desktop::crm::orders"
        }
      }
    },
    {
      "text": "Lightweight list. Reads the enabled lightweight order list and selected order with associated communications. Legacy associations can be incomplete.",
      "kind": "product",
      "entities": [
        {
          "entity": "order",
          "effect": "reads",
          "facts": [
            "Number",
            "Amount",
            "Currency",
            "Payment information",
            "Supplier information",
            "Trade terms",
            "Legacy deposits",
            "Confirmation time",
            "Notes",
            "Owner",
            "Created time",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::orders"
        },
        "da": {
          "place": "crm-desktop::crm::orders"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-contract.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-db.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/orders/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/features.ts"
    }
  ]
}
---

# Lightweight list

## Trigger

A CRM member invokes browse orders for the case “Lightweight list”.

## Outcome

Lightweight list. Reads the enabled lightweight order list and selected order with associated communications. Legacy associations can be incomplete.
