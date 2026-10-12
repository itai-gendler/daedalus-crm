---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Accept customer-profile draft”.",
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
      "text": "The pending proposal and its retained reason are reviewed.",
      "kind": "actor",
      "entities": [
        {
          "entity": "customer-draft",
          "effect": "reads",
          "facts": [
            "Reason",
            "Target",
            "Original proposed fields",
            "Decision",
            "Confirmation display time",
            "Proposed profile changes",
            "Current comparison values"
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
      "text": "Explicit confirmation of a valid profile card resolves any named active owner and unambiguous channel/referrer, merges the proposed fields into the current profile and calls saveCustomer. Referral and channel choices keep their mutual precedence and existing downstream attribution remains fixed. Successful apply makes the local card Accepted; an owner change can transfer unfinished work afterward.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Name",
            "Phone",
            "School/company",
            "Grade",
            "Major",
            "Follow-up status",
            "Decision status",
            "Expected signing date",
            "Sales owner",
            "Direct channel",
            "Referrer",
            "Attributed channel",
            "Attributed customer",
            "Channel owner",
            "Notes",
            "Last change"
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
      "kind": "product",
      "text": "If accepted profile fields change the sales owner, the Product transfers that customer’s old-owner unfinished plans/tasks and OPEN opportunities through its full-scope helper. A transfer failure can follow the saved profile.",
      "entities": [
        {
          "entity": "plan",
          "effect": "changes",
          "facts": [
            "Owner",
            "Last change"
          ]
        },
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Owner",
            "Last change"
          ]
        },
        {
          "entity": "opportunity",
          "effect": "changes",
          "facts": [
            "Owner",
            "Last change"
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
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::conversation"
        },
        "da": {
          "place": "crm-desktop::crm::conversation"
        }
      },
      "kind": "product",
      "text": "After the profile action and applicable carry-over work succeed, the process remembers the accepted decision.",
      "entities": [
        {
          "entity": "customer-draft",
          "effect": "changes",
          "facts": [
            "Decision",
            "Confirmation display time"
          ],
          "from": "Proposed",
          "to": "Accepted"
        }
      ]
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/carry-over-db.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/agent/proposals.ts"
    }
  ]
}
---

# Accept customer-profile draft

## Trigger

A CRM member invokes accept draft for the case “Accept customer-profile draft”.

## Outcome

Explicit confirmation of a valid profile card resolves any named active owner and unambiguous channel/referrer, merges the proposed fields into the current profile and calls saveCustomer. Referral and channel choices keep their mutual precedence and existing downstream attribution remains fixed. Successful apply makes the local card Accepted; an owner change can transfer unfinished work afterward.
