---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse contacts for the case “Search associated/unassigned groups”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::contacts"
        },
        "da": {
          "place": "crm-desktop::crm::contacts"
        }
      }
    },
    {
      "text": "Search associated/unassigned groups. Searches associated and unassigned contact groups. Unassigned records retain an addressable reassociation/edit/restore scope with no invented owner filter.",
      "kind": "product",
      "entities": [
        {
          "entity": "assigned-contact",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "WeChat",
            "Email",
            "Position",
            "Notes",
            "Primary",
            "Created time",
            "Last change"
          ]
        },
        {
          "entity": "unassigned-contact",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "WeChat",
            "Email",
            "Position",
            "Notes",
            "Former customer",
            "Former customer name",
            "Recoverable follow-up links",
            "Detach time",
            "Created time",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::contacts"
        },
        "da": {
          "place": "crm-desktop::crm::contacts"
        }
      }
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

# Search associated/unassigned groups

## Trigger

A CRM member invokes browse contacts for the case “Search associated/unassigned groups”.

## Outcome

Search associated/unassigned groups. Searches associated and unassigned contact groups. Unassigned records retain an addressable reassociation/edit/restore scope with no invented owner filter.
