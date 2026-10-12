---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete contact for the case “Delete associated”.",
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
      "text": "Delete associated. Deletes an associated or unassigned contact while keeping communications. Missing targets do not remove unrelated records. Surviving communications lose only this contact association; their participant text and history remain.",
      "kind": "product",
      "entities": [
        {
          "entity": "assigned-contact",
          "effect": "removes"
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
      "target": "src/app/(app)/customers/[id]/actions.ts#deleteContact"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#deleteUnassignedContact"
    }
  ]
}
---

# Delete associated

## Trigger

A CRM member invokes delete contact for the case “Delete associated”.

## Outcome

Delete associated. Deletes an associated or unassigned contact while keeping communications. Missing targets do not remove unrelated records.
