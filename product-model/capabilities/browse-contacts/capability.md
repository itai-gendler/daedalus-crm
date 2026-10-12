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
      "target": "src/app/(app)/contacts/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/contacts/ContactsView.tsx"
    }
  ]
}
---

# Browse Contacts

Searches associated and unassigned contact groups. Unassigned records retain an addressable reassociation/edit/restore scope with no invented owner filter.
