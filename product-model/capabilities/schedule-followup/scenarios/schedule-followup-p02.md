---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes schedule followup for the case “New task”.",
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
      "text": "New task. Creates a distinct appended follow-up plan or task owned by the creator; existing plans remain and date/subject/customer are checked.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "creates",
          "facts": [
            "Title",
            "Due time",
            "Owner",
            "Done",
            "Completion time",
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

# New task

## Trigger

A CRM member invokes schedule followup for the case “New task”.

## Outcome

New task. Creates a distinct appended follow-up plan or task owned by the creator; existing plans remain and date/subject/customer are checked.
