---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit signing for the case “General edit”.",
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
      "text": "General edit. General signing edit does not replay work closure. Trade edit synchronizes existing order money or conditionally backfills an older signing’s order; financial writes are transactional.",
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
    },
    {
      "text": "If this signing already has an order, synchronize its amount and currency even when the business template has returned to General. Its displayed confirmation date follows the edited signing date; other retained order fields are not replayed.",
      "kind": "product",
      "entities": [
        {
          "entity": "order",
          "effect": "changes",
          "facts": [
            "Amount",
            "Currency",
            "Confirmation time",
            "Last change"
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

# General edit

## Trigger

A CRM member invokes edit signing for the case “General edit”.

## Outcome

General edit. General signing edit does not replay work closure. Trade edit synchronizes existing order money or conditionally backfills an older signing’s order; financial writes are transactional.

## Decision points

### Surviving order

Does the edited signing already have an order?

- Yes → synchronize its supported money and displayed confirmation date.
- No → General editing creates no order.
