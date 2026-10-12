---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "release-to-pool"
    },
    {
      "type": "capability",
      "id": "claim-customer"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "opportunity"
    },
    {
      "type": "entity",
      "id": "plan"
    },
    {
      "type": "entity",
      "id": "task"
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

# Pool release retains ownership and claim commits before carried-work transfer

Manual release creates pool presence, reason/time and releasing member without changing Customer sales owner or last change. Automatic page-triggered release records no releasing member. Its current book threshold, local daily receipt, exact calendar cutoff, latest-follow-up/creation and Claim-time predicates govern selection; signed/lost and currently pooled customers are excluded. Every role in a configured native team adds the triggering member's sales ownership predicate. The daily receipt is local and written after scanning, with per-row upsert fallback for concurrent creation. Claim atomically deletes a surviving pool entry, conditionally assigns the caller and records Claim time/Claimed by; missing customers roll back that deletion. Carried unfinished old-owner work transfers afterward and can fail after claim commit.
