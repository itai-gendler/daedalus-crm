---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes load demo data for the case “Role/desktop/hosted/nonempty rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Role/desktop/hosted/nonempty rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::data"
        }
      }
    },
    {
      "text": "Failed management checks, native or hosted deployment, or a nonempty checked business set refuses seeding; existing real customer, lead, channel and opportunity work is not overwritten.",
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

# Role/desktop/hosted/nonempty rejection

## Trigger

The administrator invokes load demo data for the case “Role/desktop/hosted/nonempty rejection”.

## Outcome

Failed management checks, native or hosted deployment, or a nonempty checked business set refuses seeding; existing real customer, lead, channel and opportunity work is not overwritten.
