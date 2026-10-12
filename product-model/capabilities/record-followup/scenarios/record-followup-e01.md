---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes record followup for the case “Communication saved but extra writes partly fail”.",
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
      "text": "The communication can remain saved while optional extra plan/task/opportunity writes report individual failures.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "creates",
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
            "Last change",
            "Customer",
            "Contact",
            "Opportunity",
            "Order"
          ],
          "to": "Recorded"
        },
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Latest follow-up",
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
      "target": "src/app/(app)/customers/[id]/actions.ts#saveFollowUp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/FollowUpForm.tsx"
    }
  ]
}
---

# Communication saved but extra writes partly fail

## Trigger

A CRM member invokes record followup for the case “Communication saved but extra writes partly fail”.

## Outcome

The communication can remain saved while optional extra plan/task/opportunity writes report individual failures.
