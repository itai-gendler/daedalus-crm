---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The CRM member submits a question requesting proposed acquisition-source edits.",
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
      "text": "Produce channel draft with reason. Only an explicit prompt calls the model. Bounded owned history and supported attachments can inform an answer or a structured reason-bearing proposal. Model output does not itself write target CRM records.",
      "kind": "product",
      "entities": [
        {
          "entity": "conversation",
          "effect": "changes",
          "facts": [
            "Messages",
            "Last activity"
          ]
        },
        {
          "entity": "channel-draft",
          "effect": "creates",
          "facts": [
            "Reason",
            "Target",
            "Original proposed fields",
            "Decision",
            "Confirmation display time",
            "Name",
            "Phone",
            "Notes",
            "Owner",
            "Current comparison values"
          ],
          "to": "Proposed"
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

# Produce channel draft with reason

## Trigger

The CRM member submits a question requesting proposed acquisition-source edits.

## Outcome

Produce channel draft with reason. Only an explicit prompt calls the model. Bounded owned history and supported attachments can inform an answer or a structured reason-bearing proposal. Model output does not itself write target CRM records.
