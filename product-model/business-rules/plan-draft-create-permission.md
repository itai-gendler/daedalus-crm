---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "plan-draft",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-desktop::crm::conversation"
        },
        {
          "place": "crm-web::crm::conversation"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "contains",
          "entity": "conversation"
        },
        {
          "verb": "owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "contains",
          "entity": "conversation"
        },
        {
          "verb": "owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-manager"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "contains",
          "entity": "conversation"
        },
        {
          "verb": "owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/components/ProposalCard.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/thread-history.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/apply.ts"
    }
  ]
}
---

# Only related CRM administrators, related sales managers and related salespeople may create Plan Draft

This Rule governs create operations on Plan Draft at crm-desktop::crm::conversation and crm-web::crm::conversation.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through 对话 (contains) → Crm Account (owns) → 系统管理员 / 老板 (holds).
- The sales managers reached through 对话 (contains) → Crm Account (owns) → 销售主管 (holds).
- The salespeople reached through 对话 (contains) → Crm Account (owns) → 销售 (holds).


The relation binds the retained card to the viewer’s current conversation/process memory. It governs this card’s presentation and local decision, not server-signed issuance or creator-only backend acceptance. Structured apply input is revalidated through the supported ordinary CRM action and its actual scope; the backend does not prove that the submitted proposal was issued to this creator. Refresh/history replay restores no actionable card.
