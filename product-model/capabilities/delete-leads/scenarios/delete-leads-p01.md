---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes delete leads for the case “Delete selected leads”.",
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
      "text": "Delete selected leads. Removes selected visible leads and returns the actual deleted count. Customer history is not inferred to disappear with its original lead.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes",
          "from": "待跟进"
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

# Delete selected leads

## Trigger

A CRM member invokes delete leads for the case “Delete selected leads”.

## Outcome

Delete selected leads. Removes selected visible leads and returns the actual deleted count. Customer history is not inferred to disappear with its original lead.
