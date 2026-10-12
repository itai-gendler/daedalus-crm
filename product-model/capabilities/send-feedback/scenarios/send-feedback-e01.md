---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes send feedback for the case “Cloud/network failure”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::feedback"
        },
        "da": {
          "place": "crm-desktop::crm::feedback"
        }
      }
    },
    {
      "text": "The dependency or network error is shown; the interface does not claim that the requested save completed.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::feedback"
        },
        "da": {
          "place": "crm-desktop::crm::feedback"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/feedback/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/feedback-reply.ts"
    }
  ]
}
---

# Cloud/network failure

## Trigger

A CRM member invokes send feedback for the case “Cloud/network failure”.

## Outcome

The dependency or network error is shown; the interface does not claim that the requested save completed.
