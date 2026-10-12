---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes undo pool operation for the case “Changed ownership/claimed target/inactive prior owner skipped”.",
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
      "text": "Undo-release has no mutation when no matching caller-attributed pool row survives. Undo-claim skips preselected ownership/pool or inactive submitted-owner mismatches, and retains submitted work that is completed, reassigned or no longer attached. Eligibility preselection is not an atomic freshness guarantee for the later loop.",
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

# Changed ownership/claimed target/inactive prior owner skipped

## Trigger

A CRM member invokes undo pool operation for the case “Changed ownership/claimed target/inactive prior owner skipped”.

## Outcome

Undo-release has no mutation when no matching caller-attributed pool row survives. Undo-claim skips preselected ownership/pool or inactive submitted-owner mismatches, and retains submitted work that is completed, reassigned or no longer attached. Eligibility preselection is not an atomic freshness guarantee for the later loop.
