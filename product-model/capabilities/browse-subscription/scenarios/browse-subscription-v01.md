---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse subscription for the case “Nonhosted/no membership”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::subscription"
        }
      }
    },
    {
      "text": "The submitted request reaches this validation boundary: Nonhosted/no membership.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::subscription"
        }
      }
    },
    {
      "text": "A nonhosted deployment or missing own hosted context makes the supported subscription context unavailable; it does not present another workspace's subscription.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::subscription"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/billing/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/billing/page.tsx"
    }
  ]
}
---

# Nonhosted/no membership

## Trigger

A CRM member invokes browse subscription for the case “Nonhosted/no membership”.

## Outcome

A nonhosted deployment or missing own hosted context makes the supported subscription context unavailable; it does not present another workspace's subscription.
