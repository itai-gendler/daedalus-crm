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
      "target": "src/app/(app)/customers/[id]/actions.ts#restoreFollowUp"
    }
  ]
}
---

# Restore Followup

Restores a missing snapshot, bounded original text and surviving associations; missing optional associations and heuristic task repair have separate results.
