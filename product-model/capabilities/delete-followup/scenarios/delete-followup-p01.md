---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete followup for the case “Delete and recalculate latest follow-up”.",
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
      "text": "Delete and recalculate latest follow-up. Deletes the selected communication and recalculates latest communication by occurred time; an already completed matching task is retained.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "removes",
          "from": "Recorded"
        },
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Latest follow-up",
            "Last change"
          ]
        }
      ],
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
      "text": "If the removed communication had TASK/REMIND timing, remove its earliest matching unfinished work; completed and nonmatching work remain.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "effect": "removes",
          "from": "Unfinished"
        }
      ],
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

# Delete and recalculate latest follow-up

## Trigger

A CRM member invokes delete followup for the case “Delete and recalculate latest follow-up”.

## Outcome

Delete and recalculate latest follow-up. Deletes the selected communication and recalculates latest communication by occurred time; an already completed matching task is retained.

## Decision points

### Matching unfinished work

Does the removed communication have an earliest matching unfinished work item?

- Earliest matching unfinished work exists → remove that one item.
- Missing, completed or nonmatching work → retain it.
