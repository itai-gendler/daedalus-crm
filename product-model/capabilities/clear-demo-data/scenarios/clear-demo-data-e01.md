---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes clear demo data for the case “Nonatomic failure”.",
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
      "text": "Clearing proceeds through ordered deletions without a single atomic transaction. Failure can leave earlier deletions committed and later sets or the demo marker intact; the interface must not report that every selected set was cleared.",
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

# Nonatomic failure

## Trigger

The administrator invokes clear demo data for the case “Nonatomic failure”.

## Outcome

Clearing proceeds through ordered deletions without a single atomic transaction. Failure can leave earlier deletions committed and later sets or the demo marker intact; the interface must not report that every selected set was cleared.
