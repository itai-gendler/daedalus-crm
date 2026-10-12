---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes clear demo data for the case “Cloud identity/nondeleted sets retained”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::business-settings"
        },
        "da": {
          "place": "crm-desktop::crm::business-settings"
        }
      }
    },
    {
      "text": "Cloud identity is retained. The cleanup removes the implemented business sets, import history, prior audit history, demo marker and generated demo members; ordinary real members and sets outside those deletions are not claimed erased.",
      "kind": "product",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::business-settings"
        },
        "da": {
          "place": "crm-desktop::crm::business-settings"
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

# Cloud identity/nondeleted sets retained

## Trigger

The administrator invokes clear demo data for the case “Cloud identity/nondeleted sets retained”.

## Outcome

Cloud identity is retained. The cleanup removes the implemented business sets, import history, prior audit history, demo marker and generated demo members; ordinary real members and sets outside those deletions are not claimed erased.
