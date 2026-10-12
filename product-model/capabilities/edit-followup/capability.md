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
      "target": "src/app/(app)/customers/[id]/actions.ts#saveFollowUp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#跟着改待办"
    }
  ]
}
---

# Edit Followup

Edits validated fields without replacing original text; the actual TASK/REMIND matching heuristic adjusts eligible work and customer latest communication.
