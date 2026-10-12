---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes restore followup for the case “Missing associations/task-repair differences”.",
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
      "text": "Missing optional contacts/opportunities are restored as null associations and a missing order is not reattached. TASK/REMIND restoration counts matching unfinished communications and tasks and adds a task only when the matching task count is short. Customer latest communication is recalculated from occurred time.",
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
      "target": "src/app/(app)/customers/[id]/actions.ts#restoreFollowUp"
    }
  ]
}
---

# Missing associations/task-repair differences

## Trigger

A CRM member invokes restore followup for the case “Missing associations/task-repair differences”.

## Outcome

Missing optional contacts/opportunities are restored as null associations and a missing order is not reattached. TASK/REMIND restoration counts matching unfinished communications and tasks and adds a task only when the matching task count is short. Customer latest communication is recalculated from occurred time.
