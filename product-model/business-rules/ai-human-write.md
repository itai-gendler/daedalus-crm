---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "ask-ai"
    },
    {
      "type": "capability",
      "id": "accept-draft"
    },
    {
      "type": "capability",
      "id": "dismiss-draft"
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
      "id": "conversation"
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

# AI target writes wait for explicit human acceptance

Producing any of the eight retained draft kinds leaves the target CRM records unchanged. Accepting a valid draft performs the supported target write after explicit human confirmation; dismissing it performs no target write.
