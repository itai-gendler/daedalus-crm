---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes disable channel for the case “Missing target”.",
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
      "text": "If the selected channel disappeared, the update returns the already-gone error. The requested active flag is not written to another channel.",
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

A CRM member invokes disable channel for the case “Missing target”.

## Outcome

If the selected channel disappeared, the update returns the already-gone error. The requested active flag is not written to another channel.
