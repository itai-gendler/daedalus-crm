---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Accept follow-up draft”.",
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
          "entity": "followup-draft",
          "effect": "reads",
          "facts": [
            "Reason",
            "Target",
            "Original proposed fields",
            "Decision",
            "Confirmation display time",
            "Type",
            "Title",
            "Content",
            "Occurred time"
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
      "text": "Explicit confirmation records the proposed communication through saveFollowUp with status 已完成 and no due time. It supplies the added communication identifier for limited undo and makes the local card Accepted after successful apply. Latest-follow-up recalculation can fail after communication creation.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "creates",
          "facts": [
            "Type",
            "Title",
            "Status",
            "Participants",
            "Content",
            "Occurred time",
            "Duration",
            "Due time",
            "Original text",
            "Recording member",
            "Created time",
            "Last change",
            "Customer",
            "Contact",
            "Opportunity",
            "Order"
          ],
          "to": "Recorded"
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
      "text": "The Product recalculates Customer latest follow-up by occurred time, using a separate outer update after communication creation.",
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
      "kind": "product",
      "text": "After the action succeeds, the process remembers the accepted human decision.",
      "entities": [
        {
          "entity": "followup-draft",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts"
    }
  ]
}
---

# Accept follow-up draft

## Trigger

A CRM member invokes accept draft for the case “Accept follow-up draft”.

## Outcome

Explicit confirmation records the proposed communication through saveFollowUp with status 已完成 and no due time. It supplies the added communication identifier for limited undo and makes the local card Accepted after successful apply. Latest-follow-up recalculation can fail after communication creation.

## Edge cases

- This card records a completed communication and supplies no due time, so it does not create the heuristic unfinished reminder task.
- A later latest-follow-up update can fail after communication creation; the pending decision then remains without a universal rollback.
