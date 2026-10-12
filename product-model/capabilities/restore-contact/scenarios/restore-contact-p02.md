---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes restore contact for the case “Restore unassigned”.",
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
      "text": "Restore unassigned. Restores a missing associated or unassigned snapshot; associated restore requires a surviving customer and repairs only eligible null follow-up links.",
      "kind": "product",
      "entities": [
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
      "target": "src/app/(app)/customers/[id]/actions.ts#restoreContact"
    }
  ]
}
---

# Restore unassigned

## Trigger

A CRM member invokes restore contact for the case “Restore unassigned”.

## Outcome

Restore unassigned. Restores a missing associated or unassigned snapshot; associated restore requires a surviving customer and repairs only eligible null follow-up links.
