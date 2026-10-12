---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Accept plan draft”.",
      "kind": "actor",
      "entities": [
        {
          "entity": "plan-draft",
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
          "entity": "plan-draft",
          "effect": "reads",
          "facts": [
            "Reason",
            "Target",
            "Original proposed fields",
            "Decision",
            "Confirmation display time",
            "Subject",
            "Time",
            "Method"
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
      "text": "Explicit confirmation passes the proposed subject, time and method to savePlan for the selected customer. The ordinary plan action appends a distinct plan owned by the creator and retains existing plans. Successful apply makes the local card Accepted; this kind supplies no AI undo receipt.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "creates",
          "facts": [
            "Subject",
            "Planned time",
            "Method",
            "Owner",
            "Done",
            "Created time",
            "Last change"
          ],
          "to": "Unfinished"
        },
        {
          "entity": "plan-draft",
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

# Accept plan draft

## Trigger

A CRM member invokes accept draft for the case “Accept plan draft”.

## Outcome

Explicit confirmation passes the proposed subject, time and method to savePlan for the selected customer. The ordinary plan action appends a distinct plan owned by the creator and retains existing plans. Successful apply makes the local card Accepted; this kind supplies no AI undo receipt.
