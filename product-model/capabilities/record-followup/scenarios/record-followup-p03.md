---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes record followup for the case “Order-linked recording”.",
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
      "text": "Order-linked recording. Human recording retains validated communication and up to 5,000 characters of original text. Reviewed optional plans/tasks writes occur afterward and can partly fail; order linkage is optional. When the saved communication is TASK/REMIND with a due time and is unfinished, the applicable heuristic adds its matching unfinished work. Restoration only adds work if the matching count is short.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "creates",
          "facts": [
            "Type",
            "Title",
            "Status",
            "Participants",
            "Content",
            "Occurred time",
            "Duration",
            "Due time",
            "Original text",
            "Recording member",
            "Created time",
            "Last change",
            "Customer",
            "Contact",
            "Opportunity",
            "Order"
          ],
          "to": "Recorded"
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
      "text": "After the communication is retained, the TASK/REMIND heuristic independently creates matching unfinished work only when its due-time/status checks pass and, for restoration, the matching count is short. There is no durable one-to-one communication/work link.",
      "kind": "product",
      "entities": [
        {
          "entity": "task",
          "as": "communication-reminder",
          "effect": "creates",
          "to": "Unfinished",
          "facts": [
            "Title",
            "Due time",
            "Owner",
            "Done",
            "Completion time",
            "Created time",
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
      "text": "If the form has an eligible due plan and its complete-with-recording control remains checked, mark that plan done after the recording and selected extra-work results. Otherwise retain it unfinished.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "changes",
          "from": "Unfinished",
          "to": "Done",
          "facts": [
            "Done",
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
      "target": "src/app/(app)/customers/[id]/FollowUpForm.tsx"
    }
  ]
}
---

# Order-linked recording

## Trigger

A CRM member invokes record followup for the case “Order-linked recording”.

## Outcome

Order-linked recording. Human recording retains validated communication and up to 5,000 characters of original text. Reviewed optional plans/tasks writes occur afterward and can partly fail; order linkage is optional.

## Decision points

### Due communication work

Does the retained TASK/REMIND communication have due timing and unfinished status, and does restoration need matching work?

- TASK/REMIND, a due time and unfinished status → add matching work; restoration first checks whether matching work is short.
- Other communication → no automatic work creation.

### Due plan closure

Is there an eligible due plan whose complete-with-recording control remains checked?

- Eligible due plan and checked closure → mark it done; the offered undo reopens that plan.
- No eligible plan or unchecked closure → retain its current state.
