---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse subscription for the case “Expired entitlement with retained data”.",
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
      "text": "The subscription screen presents the workspace's retained status and expiry even when its current entitlement has expired. Expiry does not erase CRM data, and presenting transfer instructions does not activate a plan.",
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

# Expired entitlement with retained data

## Trigger

A CRM member invokes browse subscription for the case “Expired entitlement with retained data”.

## Outcome

The subscription screen presents the workspace's retained status and expiry even when its current entitlement has expired. Expiry does not erase CRM data, and presenting transfer instructions does not activate a plan.
