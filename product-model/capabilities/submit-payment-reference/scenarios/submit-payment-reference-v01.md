---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes submit payment reference for the case “Membership role/plan/reference rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Membership role/plan/reference rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::subscription"
        }
      }
    },
    {
      "text": "A failed workspace-role check, invalid plan, short/invalid trimmed reference or missing workspace refuses append; no pending payment note or activation is reported.",
      "kind": "product",
      "entities": [],
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

# Membership role/plan/reference rejection

## Trigger

A CRM member invokes submit payment reference for the case “Membership role/plan/reference rejection”.

## Outcome

A failed workspace-role check, invalid plan, short/invalid trimmed reference or missing workspace refuses append; no pending payment note or activation is reported.
