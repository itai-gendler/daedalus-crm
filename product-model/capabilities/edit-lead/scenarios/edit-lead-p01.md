---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit lead for the case “Edit, including independent converted status”.",
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
      "text": "Edit, including independent converted status. Edits validated lead facts using the version guard. Changing converted status alone creates no customer and does not substitute for the conversion link.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "changes",
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
            "Last change"
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

# Edit, including independent converted status

## Trigger

A CRM member invokes edit lead for the case “Edit, including independent converted status”.

## Outcome

Edit, including independent converted status. Edits validated lead facts using the version guard. Changing converted status alone creates no customer and does not substitute for the conversion link.
