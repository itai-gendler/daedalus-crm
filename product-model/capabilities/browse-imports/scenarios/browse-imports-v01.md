---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse imports for the case “Session rejection”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::import-history"
        },
        "da": {
          "place": "crm-desktop::crm::import-history"
        }
      }
    },
    {
      "text": "The submitted request reaches this validation boundary: Session rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::import-history"
        },
        "da": {
          "place": "crm-desktop::crm::import-history"
        }
      }
    },
    {
      "text": "The session rejection prevents the requested CRM operation from completing and is exposed through its existing login/error process.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::import-history"
        },
        "da": {
          "place": "crm-desktop::crm::import-history"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/import-actions.ts"
    }
  ]
}
---

# Session rejection

## Trigger

A CRM member invokes browse imports for the case “Session rejection”.

## Outcome

The session rejection prevents the requested CRM operation from completing and is exposed through its existing login/error process.
