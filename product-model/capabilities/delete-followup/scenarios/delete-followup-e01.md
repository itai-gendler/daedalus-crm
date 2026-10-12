---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete followup for the case “Missing target/completed matching task retained”.",
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
      "text": "A missing communication returns its missing-target error. Deleting an eligible TASK/REMIND communication affects only the oldest matching unfinished task; a completed task or nonmatching task is retained.",
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
      "target": "src/app/(app)/customers/[id]/actions.ts#deleteFollowUp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#跟着改待办"
    }
  ]
}
---

# Missing target/completed matching task retained

## Trigger

A CRM member invokes delete followup for the case “Missing target/completed matching task retained”.

## Outcome

A missing communication returns its missing-target error. Deleting an eligible TASK/REMIND communication affects only the oldest matching unfinished task; a completed task or nonmatching task is retained.
