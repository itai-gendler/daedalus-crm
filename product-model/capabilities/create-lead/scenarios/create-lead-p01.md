---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes create lead for the case “Manual creation”.",
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
      "text": "Manual creation. Validates required name, a closed status vocabulary, a free-text source of at most 30 characters (blank defaults to 其他), and masked-phone round-trip values, then saves the responsible member and source facts. A lead has no kept Channel field.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "creates",
          "facts": [
            "Name",
            "Contact",
            "Industry",
            "Phone",
            "Email",
            "Status",
            "Source",
            "Responsible member",
            "Notes",
            "Conversion time",
            "Converted customer",
            "Created time",
            "Last change"
          ],
          "to": "待跟进"
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

# Manual creation

## Trigger

A CRM member invokes create lead for the case “Manual creation”.

## Outcome

Manual creation. Validates required name, a closed status vocabulary, a free-text source of at most 30 characters (blank defaults to 其他), and masked-phone round-trip values, then saves the responsible member and source facts. A lead has no kept Channel field.
