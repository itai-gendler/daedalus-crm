---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "wa": "WA",
    "da": "DA"
  },
  "steps": [
    {
      "text": "Activate the home arrangement metric or result.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::data"
        },
        "da": {
          "place": "crm-desktop::crm::data"
        }
      },
      "capability": "browse-data"
    },
    {
      "text": "The activated work metric carries its arrangement scope into schedules.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "reads",
          "facts": [
            "Done",
            "Planned time"
          ]
        },
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Done",
            "Due time"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::data"
        },
        "da": {
          "place": "crm-desktop::crm::data"
        }
      },
      "capability": "browse-data"
    },
    {
      "text": "Inspect the arrangement list reached with its carried scope.",
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
      },
      "capability": "browse-schedules"
    },
    {
      "text": "The destination includes the applicable plans and tasks under the carried scope rather than silently substituting a plan-only count.",
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
      },
      "capability": "browse-schedules"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/DashboardView.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/follow-ups/plans/page.tsx"
    }
  ]
}
---

# Metric To Schedules

## Trigger

The activated work metric carries its arrangement scope into schedules.

## Outcome

The destination includes the applicable plans and tasks under the carried scope rather than silently substituting a plan-only count.
