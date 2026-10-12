---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes submit payment reference for the case “Append pending reference”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::subscription"
        }
      }
    },
    {
      "text": "Append pending reference. Appends a pending reference for the workspace owner. Duplicate references can append; no automatic activation or payment callback follows.",
      "kind": "product",
      "entities": [
        {
          "entity": "workspace",
          "effect": "changes",
          "facts": [
            "Payment references"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::subscription"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/billing/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/billing/page.tsx"
    }
  ]
}
---

# Append pending reference

## Trigger

A CRM member invokes submit payment reference for the case “Append pending reference”.

## Outcome

Append pending reference. Appends a pending reference for the workspace owner. Duplicate references can append; no automatic activation or payment callback follows.
