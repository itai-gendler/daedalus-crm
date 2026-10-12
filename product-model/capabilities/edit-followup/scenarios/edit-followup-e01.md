---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit followup for the case “Conflict/missing target/matching difference”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::follow-ups"
        },
        "da": {
          "place": "crm-desktop::crm::follow-ups"
        }
      }
    },
    {
      "text": "A missing communication or supplied-version mismatch refuses overwriting later values. The heuristic updates only the oldest matching unfinished task: it removes that task when reminder/task matching is lost, completes it when the edited communication is completed, or changes its title/due time. Other completed/nonmatching work is retained.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::follow-ups"
        },
        "da": {
          "place": "crm-desktop::crm::follow-ups"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#saveFollowUp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#跟着改待办"
    }
  ]
}
---

# Conflict/missing target/matching difference

## Trigger

A CRM member invokes edit followup for the case “Conflict/missing target/matching difference”.

## Outcome

A missing communication or supplied-version mismatch refuses overwriting later values. The heuristic updates only the oldest matching unfinished task: it removes that task when reminder/task matching is lost, completes it when the edited communication is completed, or changes its title/due time. Other completed/nonmatching work is retained.
