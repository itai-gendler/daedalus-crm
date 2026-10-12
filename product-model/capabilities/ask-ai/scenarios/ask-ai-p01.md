---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The CRM member submits a question requesting a customer answer.",
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
      "text": "For a new question with no selected conversation, the product starts an owned page-scoped conversation and retains the initial prompt.",
      "kind": "product",
      "entities": [
        {
          "entity": "conversation",
          "effect": "creates",
          "facts": [
            "Title",
            "Page scope",
            "Messages",
            "Created time",
            "Last activity"
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
      "text": "CRM answer. Only an explicit prompt calls the model. Bounded owned history and supported attachments can inform an answer or a structured reason-bearing proposal. Model output does not itself write target CRM records.",
      "kind": "product",
      "entities": [
        {
          "entity": "conversation",
          "effect": "changes",
          "facts": [
            "Messages",
            "Last activity"
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

# CRM answer

## Trigger

The CRM member submits a question requesting a customer answer.

## Outcome

CRM answer. Only an explicit prompt calls the model. Bounded owned history and supported attachments can inform an answer or a structured reason-bearing proposal. Model output does not itself write target CRM records.

## Decision points

### Selected conversation

Is an existing conversation selected?

- No → create the owned conversation, retain the prompt and answer in it.
- Yes → retain the prompt and answer in the selected owned conversation without recreating it.
