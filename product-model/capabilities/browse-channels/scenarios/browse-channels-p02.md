---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes browse channels for the case “Referral ranking/invitation candidates”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::channels"
        },
        "da": {
          "place": "crm-desktop::crm::channels"
        }
      }
    },
    {
      "text": "Referral ranking/invitation candidates. Shows channels, direct/inherited customer attribution, referral ranking and invitation candidates with per-currency totals.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "Notes",
            "Owner",
            "Active",
            "Created time",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::channels"
        },
        "da": {
          "place": "crm-desktop::crm::channels"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/channels/actions.ts"
    }
  ]
}
---

# Referral ranking/invitation candidates

## Trigger

A CRM member invokes browse channels for the case “Referral ranking/invitation candidates”.

## Outcome

Referral ranking/invitation candidates. Shows channels, direct/inherited customer attribution, referral ranking and invitation candidates with per-currency totals.
