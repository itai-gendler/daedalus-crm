---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes undo ai change for the case “Undo added follow-up”.",
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
      "text": "The Product deletes the submitted communication still attached to the submitted Customer.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "removes",
          "from": "Recorded"
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
      "text": "A surviving oldest heuristic-matching unfinished task is removed conditionally; no durable communication/task identity is assumed.",
      "entities": [
        {
          "entity": "task",
          "effect": "removes",
          "from": "Unfinished"
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
      "text": "After deletion and heuristic task handling, the Product recalculates Customer latest follow-up by occurred time.",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Latest follow-up",
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
      "text": "After the undo action succeeds, its matching process-memory decision and content reservation are cleared, returning the retained draft to Proposed.",
      "entities": [
        {
          "entity": "followup-draft",
          "effect": "changes",
          "facts": [
            "Decision",
            "Confirmation display time"
          ],
          "from": "Accepted",
          "to": "Proposed"
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
      "target": "src/app/(app)/customers/[id]/actions.ts"
    }
  ]
}
---

# Undo added follow-up

## Trigger

A CRM member invokes undo ai change for the case “Undo added follow-up”.

## Outcome

Undo added follow-up. Supports only undo of an added communication or a still-matching accepted status change. Missing communications or later status changes prevent restoration; an internal reservation receipt is not signed undo authority.
