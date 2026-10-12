---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "ask-ai"
    },
    {
      "type": "capability",
      "id": "explain-watchlist"
    },
    {
      "type": "capability",
      "id": "draft-message"
    },
    {
      "type": "capability",
      "id": "parse-followup-note"
    },
    {
      "type": "capability",
      "id": "generate-brief"
    },
    {
      "type": "capability",
      "id": "organize-pasted-list"
    },
    {
      "type": "capability",
      "id": "complete-model"
    },
    {
      "type": "capability",
      "id": "read-gateway-info"
    },
    {
      "type": "entity",
      "id": "channel-draft"
    },
    {
      "type": "entity",
      "id": "cloud-account"
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
      "id": "followup-draft"
    },
    {
      "type": "entity",
      "id": "lead-draft"
    },
    {
      "type": "entity",
      "id": "logged-device"
    },
    {
      "type": "entity",
      "id": "opportunity-draft"
    },
    {
      "type": "entity",
      "id": "plan-draft"
    },
    {
      "type": "entity",
      "id": "service-config"
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

# AI charging follows actual provider, entitlement and receipt boundaries

Shared/cloud calls use their implemented entitlement, rolling request and debit/refund rules. The initial gift is thirty once per account and supplied machine hash, with no daily gift. Using an own key bypasses cloud-balance charging but does not bypass every applicable request/input limit.
