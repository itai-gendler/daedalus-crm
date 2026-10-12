---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse followups for the case “Customer/order history”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::follow-ups"
        },
        "da": {
          "place": "crm-desktop::crm::follow-ups"
        }
      }
    },
    {
      "text": "Customer/order history. Inspects filtered global communications or the current customer/order history with the implemented bounds.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "reads",
          "facts": [
            "Type",
            "Title",
            "Status",
            "Participants",
            "Content",
            "Occurred time",
            "Duration",
            "Due time",
            "Original text",
            "Recording member",
            "Created time",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::follow-ups"
        },
        "da": {
          "place": "crm-desktop::crm::follow-ups"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/follow-ups/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/page.tsx"
    }
  ]
}
---

# Customer/order history

## Trigger

A CRM member invokes browse followups for the case “Customer/order history”.

## Outcome

Customer/order history. Inspects filtered global communications or the current customer/order history with the implemented bounds.
