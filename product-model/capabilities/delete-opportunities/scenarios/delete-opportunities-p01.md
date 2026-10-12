---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete opportunities for the case “Delete, retaining independent orders/follow-ups”.",
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
      "text": "Delete, retaining independent orders/follow-ups. Deletes selected opportunities while retaining independent orders and communications; links are detached and missing-target counts are reported.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "removes",
          "from": "OPEN"
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

# Delete, retaining independent orders/follow-ups

## Trigger

A CRM member invokes delete opportunities for the case “Delete, retaining independent orders/follow-ups”.

## Outcome

Delete, retaining independent orders/follow-ups. Deletes selected opportunities while retaining independent orders and communications; links are detached and missing-target counts are reported.
