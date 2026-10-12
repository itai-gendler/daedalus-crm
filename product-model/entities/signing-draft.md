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

# Signing Draft

A structured proposal retained in the current conversation process with a reason, proposed fields and a human decision. Failed acceptance remains Proposed. Decision memory survives remount but refresh and history do not restore actionable cards.

## Information kept

- **Reason** — The retained explanation supporting this proposed CRM change.
- **Target** — The subject or named target to which this proposal refers.
- **Original proposed fields** — The proposal values originally produced by the model, before unsaved form editing.
- **Decision** — The current Proposed, Accepted or Dismissed process-memory decision.
- **Confirmation display time** — The process-memory time shown after a successful human confirmation.
- **Money** — The proposed signing amount and currency presented for review.
- **Currency** — The retained currency; summaries do not combine unlike currencies.
- **Date** — The proposed signing date presented for human review.
- **Notes** — The subject’s retained notes.

## States

### Proposed

The human has not accepted or dismissed this retained proposal; a failed application leaves it in this state.

### Accepted

The supported target write succeeded after human confirmation; the process remembers the accepted decision.

### Dismissed

The human dismissed this proposal; dismissal performs no target CRM write.
