---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes reopen schedule for the case “Reopen plan”.",
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
      "text": "Reopen plan. Reopens a plan or task; task completion time is cleared.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "changes",
          "facts": [
            "Done",
            "Last change"
          ],
          "from": "Done",
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

# Reopen plan

## Trigger

A CRM member invokes reopen schedule for the case “Reopen plan”.

## Outcome

Reopen plan. Reopens a plan or task; task completion time is cleared.
