---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse followups for the case “Session/scope rejection”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::follow-ups"
        },
        "da": {
          "place": "crm-desktop::crm::follow-ups"
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
          "place": "crm-web::crm::follow-ups"
        },
        "da": {
          "place": "crm-desktop::crm::follow-ups"
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
          "place": "crm-web::crm::follow-ups"
        },
        "da": {
          "place": "crm-desktop::crm::follow-ups"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/follow-ups/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/page.tsx"
    }
  ]
}
---

# Session/scope rejection

## Trigger

A CRM member invokes browse followups for the case “Session/scope rejection”.

## Outcome

Failed session validation or current record-scope lookup prevents the requested CRM operation from completing; the request does not disclose or mutate an out-of-scope record.
