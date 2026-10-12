---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes complete schedule for the case “Complete task”.",
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
      "text": "Complete task. Completes a plan or task. Task records completion time; Plan does not. A prefilled next-plan form may open within the same working context.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Done",
            "Completion time",
            "Last change"
          ],
          "from": "Unfinished",
          "to": "Done"
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
      "target": "src/app/(app)/customers/[id]/actions.ts#completePlan"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#toggleTask"
    }
  ]
}
---

# Complete task

## Trigger

A CRM member invokes complete schedule for the case “Complete task”.

## Outcome

Complete task. Completes a plan or task. Task records completion time; Plan does not. A prefilled next-plan form may open within the same working context.
