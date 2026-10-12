---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes edit customer for the case “Invalid field/identity/source relationship”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-record"
        },
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      }
    },
    {
      "text": "The submitted request reaches this validation boundary: Invalid field/identity/source relationship.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-record"
        },
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      }
    },
    {
      "text": "An unsupported field, invalid normalized identity or invalid source/referrer/channel association refuses that edit instead of saving the requested invalid values.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customer-record"
        },
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/pool-actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/pool-db.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/check-then-write.ts"
    }
  ]
}
---

# Invalid field/identity/source relationship

## Trigger

A CRM member invokes edit customer for the case “Invalid field/identity/source relationship”.

## Outcome

An unsupported field, invalid normalized identity or invalid source/referrer/channel association refuses that edit instead of saving the requested invalid values.
