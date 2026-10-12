---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse orders for the case “Order and associated follow-ups”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::order-record"
        },
        "da": {
          "place": "crm-desktop::crm::order-record"
        }
      }
    },
    {
      "text": "Order and associated follow-ups. Reads the enabled lightweight order list and selected order with associated communications. Legacy associations can be incomplete.",
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
          "place": "crm-web::crm::order-record"
        },
        "da": {
          "place": "crm-desktop::crm::order-record"
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

# Order and associated follow-ups

## Trigger

A CRM member invokes browse orders for the case “Order and associated follow-ups”.

## Outcome

Order and associated follow-ups. Reads the enabled lightweight order list and selected order with associated communications. Legacy associations can be incomplete.
