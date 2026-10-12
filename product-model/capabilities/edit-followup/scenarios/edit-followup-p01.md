---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit followup for the case “Edit and adjust heuristic matching task”.",
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
      "text": "Edit and adjust heuristic matching task. Edits validated fields without replacing original text; the actual TASK/REMIND matching heuristic adjusts eligible work and customer latest communication.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "changes",
          "facts": [
            "Type",
            "Title",
            "Status",
            "Participants",
            "Content",
            "Occurred time",
            "Duration",
            "Due time",
            "Last change",
            "Customer",
            "Contact",
            "Opportunity",
            "Order"
          ]
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
      "text": "When the old communication no longer has matching TASK/REMIND timing, remove only its earliest matching unfinished work.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "as": "matching-work",
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
    },
    {
      "text": "When the matching communication is now completed, mark that earliest unfinished work done with its completion time.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "as": "matching-work",
          "effect": "changes",
          "from": "Unfinished",
          "to": "Done",
          "facts": [
            "Done",
            "Completion time",
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
      "text": "When TASK/REMIND timing remains unfinished, change only that earliest matching work title and due time.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "as": "matching-work",
          "effect": "changes",
          "facts": [
            "Title",
            "Due time",
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

# Edit and adjust heuristic matching task

## Trigger

A CRM member invokes edit followup for the case “Edit and adjust heuristic matching task”.

## Outcome

Edit and adjust heuristic matching task. Edits validated fields without replacing original text; the actual TASK/REMIND matching heuristic adjusts eligible work and customer latest communication.

## Decision points

### Heuristic match

The earliest same-customer, same-title, same-due-time unfinished work is the only candidate.

- No candidate → no work change.
- Matching timing removed → remove that candidate.
- Communication completed → complete that candidate.
- Matching unfinished communication retained → update that candidate title/time.
