---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes complete schedule for the case “Missing/already completed target”.",
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
      "text": "A missing selected plan or task returns its missing-record result. Repeating completion of an existing plan sets Done true again; repeating task completion also refreshes its completion time. There is no already-completed refusal.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "changes",
          "facts": [
            "Done"
          ]
        },
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Done",
            "Completion time"
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

# Missing/already completed target

## Trigger

A CRM member invokes complete schedule for the case “Missing/already completed target”.

## Outcome

A missing selected plan or task returns its missing-record result. Repeating completion of an existing plan sets Done true again; repeating task completion also refreshes its completion time. There is no already-completed refusal.
