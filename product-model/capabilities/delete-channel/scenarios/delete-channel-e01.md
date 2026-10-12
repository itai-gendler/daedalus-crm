---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete channel for the case “Missing target”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::channels"
        },
        "da": {
          "place": "crm-desktop::crm::channels"
        }
      }
    },
    {
      "text": "A missing channel returns the explicit already-gone error, including a disappearance between lookup and deletion. No other channel is deleted.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::channels"
        },
        "da": {
          "place": "crm-desktop::crm::channels"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/channels/actions.ts"
    }
  ]
}
---

# Missing target

## Trigger

A CRM member invokes delete channel for the case “Missing target”.

## Outcome

A missing channel returns the explicit already-gone error, including a disappearance between lookup and deletion. No other channel is deleted.
