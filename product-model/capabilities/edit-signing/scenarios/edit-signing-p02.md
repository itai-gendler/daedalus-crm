---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit signing for the case “Trade order-information edit”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::signing"
        },
        "da": {
          "place": "crm-desktop::crm::signing"
        }
      }
    },
    {
      "text": "Trade order-information edit. General signing edit does not replay work closure. Trade edit synchronizes existing order money or conditionally backfills an older signing’s order; financial writes are transactional.",
      "kind": "product",
      "entities": [
        {
          "entity": "signing",
          "effect": "changes",
          "facts": [
            "Amount",
            "Precise amount",
            "Currency",
            "Signing date",
            "Notes",
            "Last change"
          ]
        },
        {
          "entity": "order",
          "effect": "changes",
          "facts": [
            "Number",
            "Amount",
            "Currency",
            "Payment information",
            "Supplier information",
            "Confirmation time",
            "Last change"
          ]
        },
        {
          "entity": "supplier",
          "effect": "creates",
          "facts": [
            "Name"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::signing"
        },
        "da": {
          "place": "crm-desktop::crm::signing"
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

# Trade order-information edit

## Trigger

A CRM member invokes edit signing for the case “Trade order-information edit”.

## Outcome

Trade order-information edit. General signing edit does not replay work closure. Trade edit synchronizes existing order money or conditionally backfills an older signing’s order; financial writes are transactional.
