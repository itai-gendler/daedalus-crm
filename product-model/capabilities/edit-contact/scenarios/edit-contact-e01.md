---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit contact for the case “Version conflict/missing target”.",
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
      "text": "The version guard refuses conflicting or missing targets in the applicable associated/unassigned store.",
      "kind": "product",
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

# Version conflict/missing target

## Trigger

A CRM member invokes edit contact for the case “Version conflict/missing target”.

## Outcome

The version guard refuses conflicting or missing targets in the applicable associated/unassigned store.
