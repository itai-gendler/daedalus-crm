---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "The administrator invokes clear demo data for the case “Confirm current business data/history clearing”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::business-settings"
        },
        "da": {
          "place": "crm-desktop::crm::business-settings"
        }
      }
    },
    {
      "text": "Confirm current business data/history clearing. Confirmed marker-gated clearing removes the actual business/history sets under deployment rules. Cloud identity and nondeleted sets remain; failure can be nonatomic.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "removes"
        }
      ],
      "actor": "crm-admin",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::business-settings"
        },
        "da": {
          "place": "crm-desktop::crm::business-settings"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/lead/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/lead.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/demo-data.ts"
    }
  ]
}
---

# Confirm current business data/history clearing

## Trigger

The administrator invokes clear demo data for the case “Confirm current business data/history clearing”.

## Outcome

Confirm current business data/history clearing. Confirmed marker-gated clearing removes the actual business/history sets under deployment rules. Cloud identity and nondeleted sets remain; failure can be nonatomic.
