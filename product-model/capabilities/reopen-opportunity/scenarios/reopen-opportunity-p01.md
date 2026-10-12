---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes reopen opportunity for the case “Reopen”.",
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
      "text": "Reopen. Reopens under the linked-order guard, or restores stage/probability from undo information. Winning-stage paths do not imply identical normalization.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "changes",
          "facts": [
            "Stage",
            "Probability",
            "Status",
            "Closed time",
            "Last change"
          ],
          "from": "LOST",
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

# Reopen

## Trigger

A CRM member invokes reopen opportunity for the case “Reopen”.

## Outcome

Reopen. Reopens under the linked-order guard, or restores stage/probability from undo information. Winning-stage paths do not imply identical normalization.
