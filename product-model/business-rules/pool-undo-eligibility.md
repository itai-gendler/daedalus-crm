---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "undo-pool-operation"
    },
    {
      "type": "entity",
      "id": "customer"
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

# Pool undo restores only source-eligible submitted ownership and carried work

Undo-release removes surviving pool rows for submitted customers only where the retained releasing member matches the current account; it authenticates no original-action receipt or timestamp. Undo-claim preselects customers currently owned by the caller and outside the pool, with active submitted restoration accounts. It does not require a kept Claim to prove original claimant identity or authenticate submitted owner/work arrays. Customer ownership is restored, a manual pool entry is created for the caller, and only that caller's Claim row is deleted. Submitted carried plans/tasks restore only while still attached to the customer, caller-owned and unfinished; submitted opportunities must remain caller-owned and OPEN. These callback consequences inherit the initiating operation's decision. Preselection is not rechecked completely inside each transaction; later changes and inactive restoration accounts can yield retention or partial outcomes.
