---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes create lead for the case “Invalid required/status/source/phone facts”.",
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
      "text": "The submitted request reaches this validation boundary: Invalid required/status/source/phone facts.",
      "kind": "condition",
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
      "text": "A blank name, unknown status, source longer than 30 characters, or unrecognized masked phone produces the corresponding validation error. An arbitrary source within the length bound is accepted; blank source becomes 其他. No row containing the rejected facts is created.",
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

# Invalid required/status/source/phone facts

## Trigger

A CRM member invokes create lead for the case “Invalid required/status/source/phone facts”.

## Outcome

A blank name, unknown status, source longer than 30 characters, or unrecognized masked phone produces the corresponding validation error. An arbitrary source within the length bound is accepted; blank source becomes 其他. No row containing the rejected facts is created.
