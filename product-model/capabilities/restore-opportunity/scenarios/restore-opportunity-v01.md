---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes restore opportunity for the case “Existing target/missing customer”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::opportunities"
        },
        "da": {
          "place": "crm-desktop::crm::opportunities"
        }
      }
    },
    {
      "text": "The submitted request reaches this validation boundary: Existing target/missing customer.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::opportunities"
        },
        "da": {
          "place": "crm-desktop::crm::opportunities"
        }
      }
    },
    {
      "text": "Existing opportunities, missing parent customers and invalid stage/status snapshots are skipped. The result reports restored and not-restored counts rather than duplicating the existing opportunity.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::opportunities"
        },
        "da": {
          "place": "crm-desktop::crm::opportunities"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/opportunities/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-contract.ts"
    }
  ]
}
---

# Existing target/missing customer

## Trigger

A CRM member invokes restore opportunity for the case “Existing target/missing customer”.

## Outcome

Existing opportunities, missing parent customers and invalid stage/status snapshots are skipped. The result reports restored and not-restored counts rather than duplicating the existing opportunity.
