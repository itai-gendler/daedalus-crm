---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete contact for the case “Missing target”.",
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
      "text": "Missing targets do not delete other contacts; communication history survives.",
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

# Missing target

## Trigger

A CRM member invokes delete contact for the case “Missing target”.

## Outcome

Missing targets do not delete other contacts; communication history survives.
