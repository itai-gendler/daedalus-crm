---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes register signing for the case “General signing”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::signing"
        },
        "da": {
          "place": "crm-desktop::crm::signing"
        }
      }
    },
    {
      "text": "General signing. Checks customer/day/rounded amount/currency inside check-then-write. Positive finite precise amount and currency survive; legacy integer amount is bounded to 2,147,483,647. Trade registration creates an order transactionally; duplicate override requires manual confirmation.",
      "kind": "product",
      "entities": [
        {
          "entity": "signing",
          "effect": "creates",
          "facts": [
            "Amount",
            "Precise amount",
            "Currency",
            "Signing date",
            "Notes",
            "Frozen sales owner",
            "Frozen channel owner",
            "Prior linked opportunity stage/probability",
            "Created time",
            "Last change"
          ],
          "to": "Recorded"
        },
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Follow-up status",
            "Last change",
            "Decision status"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::signing"
        },
        "da": {
          "place": "crm-desktop::crm::signing"
        }
      }
    },
    {
      "text": "After financial registration and the customer status update, close only the selected same-customer eligible subjects: OPEN opportunities become won, unfinished plans/tasks become done. Retain prior opportunity stage/probability for a later eligible signing-deletion restoration. Unselected, other-customer or already closed work remains; closing work does not share the earlier financial transaction.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "changes",
          "from": "OPEN",
          "to": "WON",
          "facts": [
            "Status",
            "Stage",
            "Probability",
            "Closed time",
            "Last change"
          ]
        },
        {
          "entity": "plan",
          "effect": "changes",
          "from": "Unfinished",
          "to": "Done",
          "facts": [
            "Done",
            "Last change"
          ]
        },
        {
          "entity": "task",
          "effect": "changes",
          "from": "Unfinished",
          "to": "Done",
          "facts": [
            "Done",
            "Completion time",
            "Last change"
          ]
        },
        {
          "entity": "signing",
          "effect": "changes",
          "facts": [
            "Prior linked opportunity stage/probability"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::signing"
        },
        "da": {
          "place": "crm-desktop::crm::signing"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-contract.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-db.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/orders/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/features.ts"
    }
  ]
}
---

# General signing

## Trigger

A CRM member invokes register signing for the case “General signing”.

## Outcome

General signing. Checks customer/day/rounded amount/currency inside check-then-write. Positive finite precise amount and currency survive; legacy integer amount is bounded to 2,147,483,647. Trade registration creates an order transactionally; duplicate override requires manual confirmation.

## Decision points

### Selected closing work

Which same-customer subjects remain selected and eligible after financial registration?

- OPEN opportunity → try its win and retain prior stage/probability only after success.
- Unfinished plan/task → try completion.
- Unselected, other-customer or already closed subject → retain it.

### Supplier lookup

Does the trimmed supplied supplier name already exist?

- Existing exact name → reuse its lookup identity.
- New nonblank name on an enabled order write → create its lookup identity in the financial transaction.
- Blank or no order write → no new supplier.
