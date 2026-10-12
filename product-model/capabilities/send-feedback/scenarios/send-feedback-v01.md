---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes send feedback for the case “Empty/credential/selfhost unavailable”.",
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
      "text": "The submitted request reaches this validation boundary: Empty/credential/selfhost unavailable.",
      "kind": "condition",
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
      "text": "Empty feedback, invalid cloud credentials or a selfhost deployment without the supported cloud-feedback path prevents submission from being reported received.",
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

# Empty/credential/selfhost unavailable

## Trigger

A CRM member invokes send feedback for the case “Empty/credential/selfhost unavailable”.

## Outcome

Empty feedback, invalid cloud credentials or a selfhost deployment without the supported cloud-feedback path prevents submission from being reported received.
