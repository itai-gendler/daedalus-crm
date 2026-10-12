---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "ask-ai"
    },
    {
      "type": "capability",
      "id": "browse-conversations"
    },
    {
      "type": "capability",
      "id": "dismiss-draft"
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

# Conversation replay does not restore actionable draft decisions

Own history is bounded and handles missing/orphan messages. Attachments and actionable draft cards are not restored as fully usable history. Accepted/dismissed decisions and receipts survive process remount through current memory, but refresh clears that actionable memory.
