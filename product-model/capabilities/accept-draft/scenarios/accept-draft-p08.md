---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Accept channel draft”.",
      "kind": "actor",
      "entities": [
        {
          "entity": "channel-draft",
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
          "entity": "channel-draft",
          "effect": "reads",
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
      "text": "Explicit confirmation resolves exactly one existing named channel and any proposed active owner, then calls saveChannel with the supported phone/notes/owner changes. Blank phone/notes retain current values; existing customer attribution is not rewritten. Successful apply makes the local card Accepted without an AI undo receipt.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "changes",
          "facts": [
            "Phone",
            "Notes",
            "Owner",
            "Last change"
          ]
        },
        {
          "entity": "channel-draft",
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

# Accept channel draft

## Trigger

A CRM member invokes accept draft for the case “Accept channel draft”.

## Outcome

Explicit confirmation resolves exactly one existing named channel and any proposed active owner, then calls saveChannel with the supported phone/notes/owner changes. Blank phone/notes retain current values; existing customer attribution is not rewritten. Successful apply makes the local card Accepted without an AI undo receipt.

## Edge cases

- The channel name resolves one existing target; missing or ambiguous names are refused rather than creating a channel.
- Named owners must resolve uniquely to an active member; a matching current comparison snapshot is required where supplied.
