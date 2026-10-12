---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes restore opportunity for the case “Snapshot restore and still-null follow-up links”.",
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
      "text": "Snapshot restore and still-null follow-up links. Restores a missing snapshot only while its customer exists; repairs eligible still-null communication links while retaining independent current order state.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "creates",
          "facts": [
            "Name",
            "Amount",
            "Currency",
            "Stage",
            "Probability",
            "Status",
            "Owner",
            "Expected date",
            "Notes",
            "Closed time",
            "Created time",
            "Last change"
          ],
          "to": "OPEN"
        }
      ],
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

# Snapshot restore and still-null follow-up links

## Trigger

A CRM member invokes restore opportunity for the case “Snapshot restore and still-null follow-up links”.

## Outcome

Snapshot restore and still-null follow-up links. Restores a missing snapshot only while its customer exists; repairs eligible still-null communication links while retaining independent current order state.
