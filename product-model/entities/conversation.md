---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    }
  ],
  "relations": [
    {
      "entity": "status-draft",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer-draft",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "followup-draft",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "plan-draft",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "lead-draft",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "opportunity-draft",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "signing-draft",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "channel-draft",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# 对话

An account-owned page-scoped conversation. User/assistant messages and structured parts are contained information; replay does not restore actionable proposals or attachments.

## Information kept

- **Title** — The retained title used for this account, conversation, communication or task.
- **Page scope** — The stable page scope associated with the conversation history.
- **Messages** — Contained user/assistant message content and structured parts; history does not recreate attachments or actionable proposal cards.
- **Created time** — When this subject was created.
- **Last activity** — The conversation's retained latest activity time used in history ordering.
