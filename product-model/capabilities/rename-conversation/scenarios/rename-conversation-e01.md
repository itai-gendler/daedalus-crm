---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes rename conversation for the case “Target disappeared”.",
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
      "text": "A rename whose selected conversation no longer matches returns ok:false from its zero-count update. No alternative conversation title is changed.",
      "kind": "product",
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

# Target disappeared

## Trigger

A CRM member invokes rename conversation for the case “Target disappeared”.

## Outcome

A rename whose selected conversation no longer matches returns ok:false from its zero-count update. No alternative conversation title is changed.
