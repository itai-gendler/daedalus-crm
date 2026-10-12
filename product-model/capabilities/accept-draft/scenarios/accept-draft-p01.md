---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Accept status draft”.",
      "kind": "actor",
      "entities": [
        {
          "entity": "status-draft",
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
          "entity": "status-draft",
          "effect": "reads",
          "facts": [
            "Reason",
            "Target",
            "Original proposed fields",
            "Decision",
            "Confirmation display time",
            "Proposed follow-up status",
            "Proposed decision status",
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
      "text": "Explicit confirmation of a valid status card changes its selected follow-up or decision status through patchCustomer. The response carries the previous and accepted values for limited undo, and the local card becomes Accepted with a display time.",
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
        },
        {
          "entity": "status-draft",
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

# Accept status draft

## Trigger

A CRM member invokes accept draft for the case “Accept status draft”.

## Outcome

Explicit confirmation of a valid status card changes its selected follow-up or decision status through patchCustomer. The response carries the previous and accepted values for limited undo, and the local card becomes Accepted with a display time.
