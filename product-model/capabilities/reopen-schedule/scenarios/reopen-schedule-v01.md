---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes reopen schedule for the case “Session/scope rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Session/scope rejection.",
      "kind": "condition",
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
      "text": "Failed session validation or current record-scope lookup prevents the requested CRM operation from completing; the request does not disclose or mutate an out-of-scope record.",
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
      "target": "src/app/(app)/customers/[id]/actions.ts#completePlan"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#toggleTask"
    }
  ]
}
---

# Session/scope rejection

## Trigger

A CRM member invokes reopen schedule for the case “Session/scope rejection”.

## Outcome

Failed session validation or current record-scope lookup prevents the requested CRM operation from completing; the request does not disclose or mutate an out-of-scope record.
