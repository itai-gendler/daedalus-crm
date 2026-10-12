---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/components/ProposalCard.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/dashboard/apply.ts#applyProposal"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/agent/tools.ts#proposeTool"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/agent/proposals.ts"
    }
  ]
}
---

# Followup Draft

A structured proposal retained in the current conversation process with a reason, proposed fields and a human decision. Failed acceptance remains Proposed. Decision memory survives remount but refresh and history do not restore actionable cards.

## Information kept

- **Reason** — The retained explanation supporting this proposed CRM change.
- **Target** — The subject or named target to which this proposal refers.
- **Original proposed fields** — The proposal values originally produced by the model, before unsaved form editing.
- **Decision** — The current Proposed, Accepted or Dismissed process-memory decision.
- **Confirmation display time** — The process-memory time shown after a successful human confirmation.
- **Type** — The communication kind, such as its selected method of contact.
- **Title** — The retained title used for this account, conversation, communication or task.
- **Content** — The communication text to retain or, for a draft, proposed for review.
- **Occurred time** — The proposed communication occurrence time shown for review.

## States

### Proposed

The human has not accepted or dismissed this retained proposal; a failed application leaves it in this state.

### Accepted

The supported target write succeeded after human confirmation; the process remembers the accepted decision.

### Dismissed

The human dismissed this proposal; dismissal performs no target CRM write.
