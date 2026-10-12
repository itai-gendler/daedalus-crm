---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes record followup for the case “Invalid facts/association”.",
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
      "text": "The submitted request reaches this validation boundary: Invalid facts/association.",
      "kind": "condition",
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
      "text": "Unsupported communication type/status or nonfinite/negative duration returns validation failure. A missing required association can fail the save. An unsupported customer/order pairing is ignored by the order-link helper; this is not a guarantee that all association failures roll back a communication already saved.",
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
      "target": "src/app/(app)/customers/[id]/FollowUpForm.tsx"
    }
  ]
}
---

# Invalid facts/association

## Trigger

A CRM member invokes record followup for the case “Invalid facts/association”.

## Outcome

Unsupported communication type/status or nonfinite/negative duration returns validation failure. A missing required association can fail the save. An unsupported customer/order pairing is ignored by the order-link helper; this is not a guarantee that all association failures roll back a communication already saved.
