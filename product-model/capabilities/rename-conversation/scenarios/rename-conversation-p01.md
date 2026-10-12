---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes rename conversation for the case “Rename with 60-character truncation”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::home"
        },
        "da": {
          "place": "crm-desktop::crm::home"
        }
      }
    },
    {
      "text": "Rename with 60-character truncation. A nonempty title is truncated to 60 characters and saved on the owned home-history conversation. Global hosts do not gain rename controls.",
      "kind": "product",
      "entities": [
        {
          "entity": "conversation",
          "effect": "changes",
          "facts": [
            "Title"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::home"
        },
        "da": {
          "place": "crm-desktop::crm::home"
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

# Rename with 60-character truncation

## Trigger

A CRM member invokes rename conversation for the case “Rename with 60-character truncation”.

## Outcome

Rename with 60-character truncation. A nonempty title is truncated to 60 characters and saved on the owned home-history conversation. Global hosts do not gain rename controls.
