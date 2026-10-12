---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit contact for the case “Unassigned edit”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::contacts"
        },
        "da": {
          "place": "crm-desktop::crm::contacts"
        }
      }
    },
    {
      "text": "Unassigned edit. Associated and unassigned editing use their respective fact lists and version guards; only associated contacts have Primary.",
      "kind": "product",
      "entities": [
        {
          "entity": "unassigned-contact",
          "effect": "changes",
          "facts": [
            "Name",
            "Phone",
            "WeChat",
            "Email",
            "Position",
            "Notes",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::contacts"
        },
        "da": {
          "place": "crm-desktop::crm::contacts"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#saveContact"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/actions.ts#saveUnassignedContact"
    }
  ]
}
---

# Unassigned edit

## Trigger

A CRM member invokes edit contact for the case “Unassigned edit”.

## Outcome

Unassigned edit. Associated and unassigned editing use their respective fact lists and version guards; only associated contacts have Primary.
