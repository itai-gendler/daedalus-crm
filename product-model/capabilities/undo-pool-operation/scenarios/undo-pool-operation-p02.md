---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member submits undo-claim customer/old-owner pairs and optional carried-work IDs.",
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
      "text": "The Product preselects submitted customers currently sales-owned by this member and outside the pool, and submitted active restoration accounts.",
      "kind": "condition",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Sales owner",
            "Pool state"
          ]
        },
        {
          "entity": "crm-account",
          "effect": "reads",
          "facts": [
            "Active"
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
      "text": "For each preselected pair the callback restores Customer sales ownership, creates a manual pool entry attributed to the current member, and removes Claim information only when its retained member matches the current member.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "changes",
          "facts": [
            "Sales owner",
            "Last change",
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
      "text": "The same callback restores submitted carried-work IDs still attached to that Customer, caller-owned and unfinished for plans/tasks or OPEN for opportunities; other work remains.",
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

# Undo own claim

## Trigger

A CRM member invokes undo pool operation for the case “Undo own claim”.

## Outcome

Eligible submitted owner pairs restore ownership and pool presence; only the current member’s retained Claim is removed. Eligible submitted carried work restores conditionally. Claim records do not prove original-claimant provenance, and submitted old-owner/work arrays are not authenticated against an issued receipt.

## Edge cases

- Preselection precedes the transaction loop; it does not recheck every ownership and active-account predicate against intervening reassignment.
- Reassigned, completed or no-longer-attached submitted work remains. Each customer callback has its own commit/failure outcome rather than a universal batch rollback.
