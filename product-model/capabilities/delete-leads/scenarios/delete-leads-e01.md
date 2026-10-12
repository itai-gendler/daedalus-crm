---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete leads for the case “Missing-target count”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::leads"
        },
        "da": {
          "place": "crm-desktop::crm::leads"
        }
      }
    },
    {
      "text": "Already missing selections contribute no deletion and no audit entry. If every selection is missing, the operation still succeeds with deleted:0. Surviving selections follow the primary deletion case and its actual deleted count; the count is not a fabricated missing-target report.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::leads"
        },
        "da": {
          "place": "crm-desktop::crm::leads"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/leads/actions.ts"
    }
  ]
}
---

# Missing-target count

## Trigger

A CRM member invokes delete leads for the case “Missing-target count”.

## Outcome

Already missing selections contribute no deletion and no audit entry. If every selection is missing, the operation still succeeds with deleted:0. Surviving selections follow the primary deletion case and its actual deleted count; the count is not a fabricated missing-target report.
