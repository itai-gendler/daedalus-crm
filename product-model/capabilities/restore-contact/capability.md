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
      "target": "src/app/(app)/customers/[id]/actions.ts#restoreContact"
    }
  ]
}
---

# Restore Contact

Restores a missing associated or unassigned snapshot; associated restore requires a surviving customer and repairs only eligible null follow-up links.
