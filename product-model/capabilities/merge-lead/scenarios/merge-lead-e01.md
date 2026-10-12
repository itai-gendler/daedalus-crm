---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes merge lead for the case “Concurrent conversion or missing target”.",
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
      "text": "If the conversion gate loses to a concurrent request, it reports that the lead has just been converted and makes no second association. A missing/inaccessible target returns the merge refusal and creates no replacement customer.",
      "kind": "product",
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

# Concurrent conversion or missing target

## Trigger

A CRM member invokes merge lead for the case “Concurrent conversion or missing target”.

## Outcome

If the conversion gate loses to a concurrent request, it reports that the lead has just been converted and makes no second association. A missing/inaccessible target returns the merge refusal and creates no replacement customer.
