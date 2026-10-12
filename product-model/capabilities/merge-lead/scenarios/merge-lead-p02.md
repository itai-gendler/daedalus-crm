---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes merge lead for the case “Retain existing direct lead association”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::leads"
        },
        "da": {
          "place": "crm-desktop::crm::leads"
        }
      }
    },
    {
      "text": "Retain existing direct lead association. Reuses the matching visible customer and records conversion. If that customer already has a direct lead association it is retained; a hidden match does not authorize a duplicate.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
            "Status",
            "Conversion time",
            "Notes",
            "Last change"
          ],
          "from": "待跟进",
          "to": "已转化"
        },
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "Email",
            "Direct source"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::leads"
        },
        "da": {
          "place": "crm-desktop::crm::leads"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/leads/actions.ts"
    }
  ]
}
---

# Retain existing direct lead association

## Trigger

A CRM member invokes merge lead for the case “Retain existing direct lead association”.

## Outcome

Retain existing direct lead association. Reuses the matching visible customer and records conversion. If that customer already has a direct lead association it is retained; a hidden match does not authorize a duplicate.

## Edge cases

- The customer’s existing direct lead association is retained; this newly merged lead records converted status/time and an explanatory note without taking that unique association.
- The existing customer profile is not rewritten; the returned customer identifier still supports the result continuation.
