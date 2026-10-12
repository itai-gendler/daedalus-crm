---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete schedule for the case “Delete task”.",
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
      "text": "Delete task. Deletes the selected plan or task; no general arrangement restore is promised.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "removes",
          "from": "Unfinished"
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
      "target": "src/app/(app)/customers/[id]/actions.ts#deletePlan"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#deleteTask"
    }
  ]
}
---

# Delete task

## Trigger

A CRM member invokes delete schedule for the case “Delete task”.

## Outcome

Delete task. Deletes the selected plan or task; no general arrangement restore is promised.
