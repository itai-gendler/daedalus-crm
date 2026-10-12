---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes rename conversation for the case “Empty/inaccessible title”.",
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
      "text": "The submitted request reaches this validation boundary: Empty/inaccessible title.",
      "kind": "condition",
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
      "text": "A blank trimmed title or inaccessible conversation refuses the rename; the existing conversation title is retained.",
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

# Empty/inaccessible title

## Trigger

A CRM member invokes rename conversation for the case “Empty/inaccessible title”.

## Outcome

A blank trimmed title or inaccessible conversation refuses the rename; the existing conversation title is retained.
