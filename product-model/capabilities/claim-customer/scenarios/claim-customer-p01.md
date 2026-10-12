---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes claim customer for the case “Claim and transfer unfinished work”.",
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
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      },
      "text": "The Product deletes a surviving pool row inside its full-scope callback, records Claim time and Claimed by, and conditionally assigns the current member. A missing Customer rolls that deletion back.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by"
          ]
        }
      ]
    },
    {
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      },
      "text": "If the old sales owner differs, the same callback changes Customer sales ownership and its last-change time.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Sales owner",
            "Last change"
          ]
        }
      ]
    },
    {
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::customers"
        },
        "da": {
          "place": "crm-desktop::crm::customers"
        }
      },
      "text": "After successful claims commit, the Product transfers the old owner’s unfinished plans/tasks and OPEN opportunities for those customers and returns the actual carried IDs/counts.",
      "kind": "product",
      "entities": [
        {
          "entity": "plan",
          "effect": "changes",
          "facts": [
            "Owner",
            "Last change"
          ]
        },
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Owner",
            "Last change"
          ]
        },
        {
          "entity": "opportunity",
          "effect": "changes",
          "facts": [
            "Owner",
            "Last change"
          ]
        }
      ]
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

# Claim and transfer unfinished work

## Trigger

A CRM member invokes claim customer for the case “Claim and transfer unfinished work”.

## Outcome

Successful pool deletion commits one claim per customer, clears current Pool entry/Released by and records the member’s claim. Ownership changes only when needed. Eligible carried work follows afterward; that transfer can fail after the customer claim has committed.

## Edge cases

- No surviving pool row counts unchanged. A missing customer rolls back its pool deletion; another successful claimant cannot have its pool row consumed again.
- Preliminary legacy signing-owner backfill uses its separate call path; carried-work callbacks and caught audit failure do not establish a uniform workspace-expiry gate or rollback.
