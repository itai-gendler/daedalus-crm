---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes schedule followup for the case “New plan”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::schedules"
        },
        "da": {
          "place": "crm-desktop::crm::schedules"
        }
      }
    },
    {
      "text": "New plan. Creates a distinct appended follow-up plan or task owned by the creator; existing plans remain and date/subject/customer are checked.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "creates",
          "facts": [
            "Subject",
            "Planned time",
            "Method",
            "Owner",
            "Done",
            "Created time",
            "Last change"
          ],
          "to": "Unfinished"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::schedules"
        },
        "da": {
          "place": "crm-desktop::crm::schedules"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#savePlan"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#saveTask"
    }
  ]
}
---

# New plan

## Trigger

A CRM member invokes schedule followup for the case “New plan”.

## Outcome

New plan. Creates a distinct appended follow-up plan or task owned by the creator; existing plans remain and date/subject/customer are checked.
