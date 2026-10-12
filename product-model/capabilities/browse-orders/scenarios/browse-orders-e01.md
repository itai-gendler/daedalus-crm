---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse orders for the case “Empty/missing/legacy association”.",
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
      "text": "No matching records produce an empty result. A bounded result retains its limit and does not claim the omitted records are absent.",
      "kind": "product",
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

# Empty/missing/legacy association

## Trigger

A CRM member invokes browse orders for the case “Empty/missing/legacy association”.

## Outcome

No matching records produce an empty result. A bounded result retains its limit and does not claim the omitted records are absent.
