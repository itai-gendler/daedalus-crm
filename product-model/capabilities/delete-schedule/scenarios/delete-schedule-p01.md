---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete schedule for the case “Delete plan”.",
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
      "text": "Delete plan. Deletes the selected plan or task; no general arrangement restore is promised.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
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

# Delete plan

## Trigger

A CRM member invokes delete schedule for the case “Delete plan”.

## Outcome

Delete plan. Deletes the selected plan or task; no general arrangement restore is promised.
