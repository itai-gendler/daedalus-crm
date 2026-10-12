---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete contact for the case “Delete unassigned”.",
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
      "text": "Delete unassigned. Deletes an associated or unassigned contact while keeping communications. Missing targets do not remove unrelated records.",
      "kind": "product",
      "entities": [
        {
          "entity": "unassigned-contact",
          "effect": "removes",
          "from": "Unassigned"
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

# Delete unassigned

## Trigger

A CRM member invokes delete contact for the case “Delete unassigned”.

## Outcome

Delete unassigned. Deletes an associated or unassigned contact while keeping communications. Missing targets do not remove unrelated records.
