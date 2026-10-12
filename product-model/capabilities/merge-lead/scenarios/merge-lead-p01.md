---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes merge lead for the case “Merge matching customer”.",
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
      "text": "Merge matching customer. Reuses the matching visible customer and records conversion. If that customer already has a direct lead association it is retained; a hidden match does not authorize a duplicate.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
            "Status",
            "Conversion time",
            "Converted customer",
            "Last change"
          ]
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

# Merge matching customer

## Trigger

A CRM member invokes merge lead for the case “Merge matching customer”.

## Outcome

Merge matching customer. Reuses the matching visible customer and records conversion. If that customer already has a direct lead association it is retained; a hidden match does not authorize a duplicate.
