---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "wa": "WA",
    "da": "DA"
  },
  "steps": [
    {
      "text": "Choose to turn the selected Trade opportunity into an order.",
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
      },
      "capability": "mark-won"
    },
    {
      "text": "The trade winning control carries the selected opportunity into financial registration and the order outcome.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "reads",
          "facts": [
            "Name",
            "Amount",
            "Currency",
            "Stage",
            "Status"
          ]
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
      },
      "capability": "mark-won"
    },
    {
      "text": "Review its prefilled amount/currency, supported order information and selected closing work, then confirm.",
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
      },
      "capability": "register-signing"
    },
    {
      "text": "The Product saves the financial registration and its template-selected lightweight order before subsequent customer and closing-work changes.",
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
          "entity": "order",
          "effect": "creates",
          "facts": [
            "Number",
            "Amount",
            "Currency",
            "Payment information",
            "Supplier information",
            "Trade terms",
            "Legacy deposits",
            "Confirmation time",
            "Notes",
            "Owner",
            "Created time",
            "Last change"
          ],
          "to": "Recorded",
          "with": "signing"
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
      },
      "capability": "register-signing"
    },
    {
      "text": "The Product updates the customer follow-up and decision status after the financial commit.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Follow-up status",
            "Decision status",
            "Last change"
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
      },
      "capability": "register-signing"
    },
    {
      "text": "The Product closes the selected same-customer OPEN opportunity and eligible selected unfinished plans/tasks; unselected or already closed work stays unchanged.",
      "kind": "product",
      "entities": [
        {
          "entity": "opportunity",
          "effect": "changes",
          "facts": [
            "Status",
            "Stage",
            "Probability",
            "Closed time",
            "Last change"
          ],
          "from": "OPEN",
          "to": "WON"
        },
        {
          "entity": "plan",
          "effect": "changes",
          "facts": [
            "Done",
            "Last change"
          ],
          "from": "Unfinished",
          "to": "Done"
        },
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Done",
            "Completion time",
            "Last change"
          ],
          "from": "Unfinished",
          "to": "Done"
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
      },
      "capability": "register-signing"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/opportunities/OpportunitiesView.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/ContractForm.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    }
  ]
}
---

# Winning Opportunity Trade Order

## Trigger

The trade winning control carries the selected opportunity into financial registration and the order outcome.

## Outcome

The new financial registration creates its lightweight order and closes the selected eligible opportunity. The selected subject is carried throughout; cancellation creates neither that registration nor its order.
