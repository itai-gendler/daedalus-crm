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
      "target": "src/app/(app)/customers/[id]/actions.ts#detachContact"
    }
  ]
}
---

# Detach Contact

Moves a contact to unassigned, retaining former customer name/context and recoverable follow-up links; former Primary is not kept in the unassigned record.
