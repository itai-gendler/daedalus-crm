---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse schedules for the case “Empty/undated/bounded result”.",
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
      "text": "Undated tasks retain their separate undated presentation. Completed plans and completed tasks are each fetched up to the latest 200; plan completion is approximated from Last change, while task Completion time is kept. Empty groups do not remove retained work.",
      "kind": "product",
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
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/follow-ups/plans/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/follow-ups/plans/PlansView.tsx"
    }
  ]
}
---

# Empty/undated/bounded result

## Trigger

A CRM member invokes browse schedules for the case “Empty/undated/bounded result”.

## Outcome

Undated tasks retain their separate undated presentation. Completed plans and completed tasks are each fetched up to the latest 200; plan completion is approximated from Last change, while task Completion time is kept. Empty groups do not remove retained work.
