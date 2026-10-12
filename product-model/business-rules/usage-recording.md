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
      "id": "model-usage-log"
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
      "target": "prisma/schema.prisma"
    }
  ]
}
---

# Provider usage records retain only available attributed usage

Supported provider calls record available model, feature, owner and input/output tokens in the visible operations usage log. Missing provider/stream usage or best-effort logging failure remains missing history; the product does not fabricate zero-token records or reconstruct that usage later.
