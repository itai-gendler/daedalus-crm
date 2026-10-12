---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Accept opportunity draft”.",
      "kind": "actor",
      "entities": [
        {
          "entity": "opportunity-draft",
          "effect": "reads",
          "facts": [
            "Reason",
            "Target",
            "Original proposed fields",
            "Decision"
          ]
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
      "text": "The pending proposal and its retained reason are reviewed.",
      "kind": "actor",
      "entities": [
        {
          "entity": "opportunity-draft",
          "effect": "reads",
          "facts": [
            "Reason",
            "Target",
            "Original proposed fields",
            "Decision",
            "Confirmation display time",
            "Proposed opportunity facts"
          ]
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
      "text": "Explicit confirmation passes the proposed amount, currency, stage, probability, date and notes to saveOpportunity. The name can default from the customer; the new opportunity is OPEN and its owner follows that customer’s current sales owner. Successful apply makes the local card Accepted without an AI undo receipt.",
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
        },
        {
          "entity": "opportunity-draft",
          "effect": "changes",
          "facts": [
            "Decision",
            "Confirmation display time"
          ],
          "from": "Proposed",
          "to": "Accepted"
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

# Accept opportunity draft

## Trigger

A CRM member invokes accept draft for the case “Accept opportunity draft”.

## Outcome

Explicit confirmation passes the proposed amount, currency, stage, probability, date and notes to saveOpportunity. The name can default from the customer; the new opportunity is OPEN and its owner follows that customer’s current sales owner. Successful apply makes the local card Accepted without an AI undo receipt.
