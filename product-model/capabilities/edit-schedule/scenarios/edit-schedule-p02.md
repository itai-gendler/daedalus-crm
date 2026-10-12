---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit schedule for the case “Edit task”.",
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
      "text": "Edit task. Edits the selected plan or task under its input and version guard.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Title",
            "Due time",
            "Last change"
          ]
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

# Edit task

## Trigger

A CRM member invokes edit schedule for the case “Edit task”.

## Outcome

Edit task. Edits the selected plan or task under its input and version guard.
