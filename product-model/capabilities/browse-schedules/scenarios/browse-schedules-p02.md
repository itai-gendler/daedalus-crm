---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse schedules for the case “Completed scope”.",
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
      "text": "Completed scope. Shows grouped plans/tasks and completed scope, including undated and bounded results. Only Task keeps completion time; plan display approximates it from last change.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "reads",
          "facts": [
            "Subject",
            "Planned time",
            "Method",
            "Owner",
            "Done",
            "Created time",
            "Last change"
          ]
        },
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Title",
            "Due time",
            "Owner",
            "Done",
            "Completion time",
            "Created time",
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

# Completed scope

## Trigger

A CRM member invokes browse schedules for the case “Completed scope”.

## Outcome

Completed scope. Shows grouped plans/tasks and completed scope, including undated and bounded results. Only Task keeps completion time; plan display approximates it from last change.
