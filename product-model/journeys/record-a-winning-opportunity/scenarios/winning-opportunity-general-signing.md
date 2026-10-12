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
      "text": "Choose financial registration while marking the selected General opportunity won.",
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
      "text": "The general winning control carries the selected opportunity and prefilled money into registration.",
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
      "text": "Confirm the carried amount/currency and signing date in the registration process.",
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
      "text": "The Product saves the financial registration before subsequent customer and closing-work changes.",
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
      "text": "The Product closes the selected same-customer OPEN opportunity and records its prior stage/probability for reversal. This General winning control does not submit plan/task selections.",
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

# Winning Opportunity General Signing

## Trigger

The general winning control carries the selected opportunity and prefilled money into registration.

## Outcome

A financial registration for the selected customer is saved and the selected eligible opportunity becomes WON. This General control submits no plan/task closure selection. Its failed signing attempt can still fall back to marking the opportunity won; the separate acceptance cases preserve that outcome.
