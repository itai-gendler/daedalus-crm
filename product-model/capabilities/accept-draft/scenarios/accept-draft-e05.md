---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes accept draft for the case “Lead apply conflict/duplicate/dependency outcome”.",
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
      "text": "Repeated same-content Lead confirmation within ten minutes is refused. Invalid supported Lead input or ordinary save failure releases the reservation and leaves the card Proposed, without claiming another independent Lead was successfully created.",
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

# Lead apply conflict/duplicate/dependency outcome

## Trigger

A CRM member invokes accept draft for the case “Lead apply conflict/duplicate/dependency outcome”.

## Outcome

Repeated same-content Lead confirmation within ten minutes is refused. Invalid supported Lead input or ordinary save failure releases the reservation and leaves the card Proposed, without claiming another independent Lead was successfully created.
