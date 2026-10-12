---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes load demo data for the case “Partial failure without atomic guarantee”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::data"
        }
      }
    },
    {
      "text": "Seeding is not one atomic operation. Failure can leave some sample data without the final demo marker, so the interface does not report that the complete sample set loaded or that the book remains empty.",
      "kind": "product",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::data"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/lead/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/lead.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/demo-data.ts"
    }
  ]
}
---

# Partial failure without atomic guarantee

## Trigger

The administrator invokes load demo data for the case “Partial failure without atomic guarantee”.

## Outcome

Seeding is not one atomic operation. Failure can leave some sample data without the final demo marker, so the interface does not report that the complete sample set loaded or that the book remains empty.
