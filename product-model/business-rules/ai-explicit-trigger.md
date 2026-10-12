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
      "id": "recognize-import-columns"
    },
    {
      "type": "entity",
      "id": "ai-config"
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
      "id": "followup-draft"
    },
    {
      "type": "entity",
      "id": "lead-draft"
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

# AI generation starts from an explicit action

Ordinary page load does not start proposal generation or write CRM. An explicit question/preparation action starts the provider work. Started jobs can continue across view remount; that continuation does not constitute human acceptance of a proposed CRM change.
