---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes detach contact for the case “Move to unassigned, retaining former context”.",
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
      "text": "Move to unassigned, retaining former context. Moves a contact to unassigned, retaining former customer name/context and recoverable follow-up links; former Primary is not kept in the unassigned record.",
      "kind": "product",
      "entities": [
        {
          "entity": "assigned-contact",
          "effect": "removes"
        },
        {
          "entity": "unassigned-contact",
          "effect": "creates",
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
          ],
          "to": "Unassigned"
        },
        {
          "entity": "follow-up",
          "effect": "changes",
          "facts": [
            "Contact"
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
      "target": "src/app/(app)/customers/[id]/actions.ts#detachContact"
    }
  ]
}
---

# Move to unassigned, retaining former context

## Trigger

A CRM member invokes detach contact for the case “Move to unassigned, retaining former context”.

## Outcome

Move to unassigned, retaining former context. Moves a contact to unassigned, retaining former customer name/context and recoverable follow-up links; former Primary is not kept in the unassigned record.
