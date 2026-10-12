---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes send feedback for the case “Desktop forwarding”.",
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
      "text": "Desktop forwarding. Hosted submission saves bounded feedback; native submission forwards to cloud with applicable credentials. Empty input, selfhost unavailability and network failure are visible.",
      "kind": "product",
      "entities": [
        {
          "entity": "feedback",
          "effect": "creates",
          "facts": [
            "Body",
            "Page",
            "Version",
            "System",
            "Account/contact",
            "Submitted time",
            "Handled",
            "Replies"
          ],
          "to": "Unhandled"
        }
      ],
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

# Desktop forwarding

## Trigger

A CRM member invokes send feedback for the case “Desktop forwarding”.

## Outcome

Desktop forwarding. Hosted submission saves bounded feedback; native submission forwards to cloud with applicable credentials. Empty input, selfhost unavailability and network failure are visible.
