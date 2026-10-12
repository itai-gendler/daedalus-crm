---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "Customers or Dashboard loads after resolving its triggering member; Dashboard has already passed the initial-template redirect.",
      "kind": "condition",
      "entities": [
        {
          "entity": "business-config",
          "effect": "reads",
          "facts": [
            "Pool threshold"
          ]
        }
      ],
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      },
      "unattended": true
    },
    {
      "text": "The Product creates automatic pool entries for rows passing the current threshold, exact calendar cutoff and Claim protection, retaining sales ownership and Customer last change and recording no releasing member.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Pool state",
            "Pool entry"
          ]
        }
      ],
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
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      },
      "text": "The book-local daily receipt is written after scanning; concurrent pool-row creation falls back to per-row upsert, and best-effort audit failure does not undo entries.",
      "kind": "product",
      "entities": []
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/page.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/page.tsx"
    }
  ]
}
---

# Page-triggered unattended eligible release

## Trigger

Customers or Dashboard loads after resolving its triggering member; Dashboard has already passed the initial-template redirect.

## Outcome

Eligible rows enter the pool with automatic reason/time, no releasing member and no ownership or Customer last-change mutation. Zero threshold or a matching local-day receipt skips scanning. In a retained native team, every role scans only its triggering member’s sales-owned rows; otherwise the ordinary query wrapper supplies scope.

## Edge cases

- The cutoff is startOf("day").subtract(poolDays - 1, "day"); latest follow-up or creation and any Claim time must be strictly earlier. Signed/lost customers and existing pool entries are excluded.
- The local daily receipt is not synchronized or an atomic scan reservation; concurrent pages may enter the scan before it is written.
