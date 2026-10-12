---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes submit payment reference for the case “Duplicate append/storage failure”.",
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
      "text": "Each submission appends a dated pending-check note instead of replacing earlier references. Repeating a reference can append it again; a failed note update is not reported saved.",
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

# Duplicate append/storage failure

## Trigger

A CRM member invokes submit payment reference for the case “Duplicate append/storage failure”.

## Outcome

Each submission appends a dated pending-check note instead of replacing earlier references. Repeating a reference can append it again; a failed note update is not reported saved.
