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
      "target": "src/app/(app)/customers/[id]/FollowUpForm.tsx"
    }
  ]
}
---

# Record Followup

Human recording retains validated communication and up to 5,000 characters of original text. Reviewed optional plans/tasks writes occur afterward and can partly fail; order linkage is optional.
