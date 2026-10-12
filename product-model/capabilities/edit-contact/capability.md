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
      "target": "src/app/(app)/customers/[id]/actions.ts#saveContact"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#saveUnassignedContact"
    }
  ]
}
---

# Edit Contact

Associated and unassigned editing use their respective fact lists and version guards; only associated contacts have Primary.
