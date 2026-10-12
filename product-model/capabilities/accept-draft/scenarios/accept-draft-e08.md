---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Channel apply conflict/duplicate/dependency outcome”.",
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
      "text": "Missing or ambiguous named channel/owner or supplied stale phone/notes comparison refuses the channel apply. Failed save releases its reservation and leaves the local card Proposed. It does not guess a channel, create a replacement channel or rewrite previously attributed customers.",
      "kind": "product",
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

# Channel apply conflict/duplicate/dependency outcome

## Trigger

A CRM member invokes accept draft for the case “Channel apply conflict/duplicate/dependency outcome”.

## Outcome

Missing or ambiguous named channel/owner or supplied stale phone/notes comparison refuses the channel apply. Failed save releases its reservation and leaves the local card Proposed. It does not guess a channel, create a replacement channel or rewrite previously attributed customers.
