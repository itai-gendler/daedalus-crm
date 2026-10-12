---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Signing apply conflict/duplicate/dependency outcome”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::conversation"
        },
        "da": {
          "place": "crm-desktop::crm::conversation"
        }
      }
    },
    {
      "text": "If the initial save commits before the later dependent step fails, these saved records/fields remain. A pre-save validation or transaction refusal contributes no such committed write.",
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
          "place": "crm-web::crm::conversation"
        },
        "da": {
          "place": "crm-desktop::crm::conversation"
        }
      }
    },
    {
      "text": "A duplicate signing by money/date/currency refuses without forcing another financial registration. Financial transaction failure rolls back its signing and dependent order. If that transaction commits and the later customer-status update fails, the financial record can remain while acceptance fails, its reservation releases and the local card stays Proposed. This card submits no selected opportunity/plan/task closure.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::conversation"
        },
        "da": {
          "place": "crm-desktop::crm::conversation"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/ai.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/apply.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/components/ProposalCard.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ai-jobs.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/thread-history.ts"
    }
  ]
}
---

# Signing apply conflict/duplicate/dependency outcome

## Trigger

A CRM member invokes accept draft for the case “Signing apply conflict/duplicate/dependency outcome”.

## Outcome

A duplicate signing by money/date/currency refuses without forcing another financial registration. Financial transaction failure rolls back its signing and dependent order. If that transaction commits and the later customer-status update fails, the financial record can remain while acceptance fails, its reservation releases and the local card stays Proposed. This card submits no selected opportunity/plan/task closure.

## Edge cases

- Duplicate money/date/currency refuses without forcing a duplicate; the draft remains Proposed.
- Financial transaction failure rolls back signing/order work. A later customer-status failure can occur after a financial commit; a failed acceptance response does not prove that financial data is absent.
