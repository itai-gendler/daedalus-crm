---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes complete schedule for the case “Complete plan”.",
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
      "text": "Complete plan. Completes a plan or task. Task records completion time; Plan does not. A prefilled next-plan form may open within the same working context.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "changes",
          "facts": [
            "Done",
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

# Complete plan

## Trigger

A CRM member invokes complete schedule for the case “Complete plan”.

## Outcome

Complete plan. Completes a plan or task. Task records completion time; Plan does not. A prefilled next-plan form may open within the same working context.
