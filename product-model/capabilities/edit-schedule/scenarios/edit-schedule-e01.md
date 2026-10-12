---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit schedule for the case “Version conflict/missing target”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::schedules"
        },
        "da": {
          "place": "crm-desktop::crm::schedules"
        }
      }
    },
    {
      "text": "A version conflict is returned instead of overwriting the later saved values.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::schedules"
        },
        "da": {
          "place": "crm-desktop::crm::schedules"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#savePlan"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#saveTask"
    }
  ]
}
---

# Version conflict/missing target

## Trigger

A CRM member invokes edit schedule for the case “Version conflict/missing target”.

## Outcome

A version conflict is returned instead of overwriting the later saved values.
