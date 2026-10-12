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
      "target": "src/app/(app)/customers/[id]/actions.ts#saveUnassignedContact"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#undoDetachContact"
    }
  ]
}
---

# Attach Contact

Associates an unassigned contact with the selected customer. Former-customer restoration repairs only eligible null communication links; a different customer receives no former links.
