---
{
  "kind": "validation",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes release to pool for the case “Release-check rejection”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      }
    },
    {
      "text": "Submitted rows fail the release branch’s actual check and none can be released.",
      "kind": "condition",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      }
    },
    {
      "text": "The Product returns the release refusal without creating a pool entry for those rows.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      }
    }
  ],
  "references": [
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
      "target": "src/lib/pool.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/carry-over-db.ts"
    }
  ]
}
---

# Release-check rejection

## Trigger

A CRM member invokes release to pool for the case “Release-check rejection”.

## Outcome

The Product returns the release refusal without creating a pool entry for those rows.
