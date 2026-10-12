---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse conversations for the case “Own page-scoped and home history”.",
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
      "text": "Own page-scoped and home history. Reads the initiating account’s selected page-scoped or home history. Orphan message handling and bounded replay do not restore attachments or actionable proposals.",
      "kind": "product",
      "entities": [
        {
          "entity": "conversation",
          "effect": "reads",
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

# Own page-scoped and home history

## Trigger

A CRM member invokes browse conversations for the case “Own page-scoped and home history”.

## Outcome

Own page-scoped and home history. Reads the initiating account’s selected page-scoped or home history. Orphan message handling and bounded replay do not restore attachments or actionable proposals.
