---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes restore contact for the case “Restore associated”.",
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
      "text": "Restore associated. Restores a missing associated or unassigned snapshot; associated restore requires a surviving customer and repairs only eligible null follow-up links. Only surviving still-null communications regain this contact association.",
      "kind": "product",
      "entities": [
        {
          "entity": "assigned-contact",
          "effect": "creates",
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
          "entity": "follow-up",
          "effect": "changes",
          "facts": [
            "Contact",
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
      "target": "src/app/(app)/customers/[id]/actions.ts#restoreContact"
    }
  ]
}
---

# Restore associated

## Trigger

A CRM member invokes restore contact for the case “Restore associated”.

## Outcome

Restore associated. Restores a missing associated or unassigned snapshot; associated restore requires a surviving customer and repairs only eligible null follow-up links.
