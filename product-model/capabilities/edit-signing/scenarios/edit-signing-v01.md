---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit signing for the case “Money/currency/duplicate/order constraint”.",
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
      "text": "The submitted request reaches this validation boundary: Money/currency/duplicate/order constraint.",
      "kind": "condition",
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
      "text": "Invalid money/currency, duplicate-signing information or a guarded existing-order constraint prevents the rejected edit from being reported saved.",
      "kind": "product",
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

# Money/currency/duplicate/order constraint

## Trigger

A CRM member invokes edit signing for the case “Money/currency/duplicate/order constraint”.

## Outcome

Invalid money/currency, duplicate-signing information or a guarded existing-order constraint prevents the rejected edit from being reported saved.
