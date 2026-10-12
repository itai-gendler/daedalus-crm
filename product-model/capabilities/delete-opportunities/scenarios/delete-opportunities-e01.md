---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete opportunities for the case “Missing-target count”.",
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
      "text": "Already missing selections contribute no snapshot. An entirely missing selection succeeds with an empty undo snapshot; surviving selected records follow the primary deletion case. Existing communication history survives with its removed opportunity link cleared.",
      "kind": "product",
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

# Missing-target count

## Trigger

A CRM member invokes delete opportunities for the case “Missing-target count”.

## Outcome

Already missing selections contribute no snapshot. An entirely missing selection succeeds with an empty undo snapshot; surviving selected records follow the primary deletion case. Existing communication history survives with its removed opportunity link cleared.
