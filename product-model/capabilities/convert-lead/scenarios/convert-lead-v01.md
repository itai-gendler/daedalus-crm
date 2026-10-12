---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes convert lead for the case “Missing identity/already converted”.",
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
      "text": "The submitted request reaches this validation boundary: Missing identity/already converted.",
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
      "text": "An already directly converted lead refuses conversion. General conversion requires a valid normalized phone; trade conversion may use its supported email identity. Missing usable identity returns the request to correction and creates no customer.",
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

# Missing identity/already converted

## Trigger

A CRM member invokes convert lead for the case “Missing identity/already converted”.

## Outcome

An already directly converted lead refuses conversion. General conversion requires a valid normalized phone; trade conversion may use its supported email identity. Missing usable identity returns the request to correction and creates no customer.
