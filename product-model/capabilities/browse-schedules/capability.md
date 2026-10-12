---
{
  "availability": [
    {
      "place": "crm-web::crm"
    },
    {
      "place": "crm-desktop::crm"
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

# Browse Schedules

Shows grouped plans/tasks and completed scope, including undated and bounded results. Only Task keeps completion time; plan display approximates it from last change.
