---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "accept-draft"
    },
    {
      "type": "entity",
      "id": "channel"
    },
    {
      "type": "entity",
      "id": "channel-draft"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "customer-draft"
    },
    {
      "type": "entity",
      "id": "follow-up"
    },
    {
      "type": "entity",
      "id": "followup-draft"
    },
    {
      "type": "entity",
      "id": "lead"
    },
    {
      "type": "entity",
      "id": "lead-draft"
    },
    {
      "type": "entity",
      "id": "opportunity"
    },
    {
      "type": "entity",
      "id": "opportunity-draft"
    },
    {
      "type": "entity",
      "id": "order"
    },
    {
      "type": "entity",
      "id": "plan"
    },
    {
      "type": "entity",
      "id": "plan-draft"
    },
    {
      "type": "entity",
      "id": "signing"
    },
    {
      "type": "entity",
      "id": "signing-draft"
    },
    {
      "type": "entity",
      "id": "status-draft"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/apply.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/credits.ts"
    }
  ]
}
---

# Draft acceptance validates current facts and releases failed reservations

Acceptance validates the draft kind, supported fields, current target, applicable comparison snapshots and name resolution. Ambiguous or inactive named members are refused. A ten-minute content reservation deduplicates supported writes; failed reservations are released. Failed stale acceptance leaves the draft Proposed.
