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
      "target": "src/app/(app)/dashboard/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/Board.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/overview/DataShell.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/overview/data.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/reports/ReportsView.tsx"
    }
  ]
}
---

# Browse Data

Shows personal home/empty start, current funnel, month or year metrics; keeps unlike currencies separate and uses bounded detail. Metric activation carries its actual filter/subject.
