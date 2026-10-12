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
    }
  ]
}
---

# Channel Draft

A structured proposal retained in the current conversation process with a reason, proposed fields and a human decision. Failed acceptance remains Proposed. Decision memory survives remount but refresh and history do not restore actionable cards.

## Information kept

- **Reason** — The retained explanation supporting this proposed CRM change.
- **Target** — The subject or named target to which this proposal refers.
- **Original proposed fields** — The proposal values originally produced by the model, before unsaved form editing.
- **Decision** — The current Proposed, Accepted or Dismissed process-memory decision.
- **Confirmation display time** — The process-memory time shown after a successful human confirmation.
- **Name** — The displayed identity of this subject.
- **Phone** — The recorded phone value under the subject’s identity/validation rules.
- **Notes** — The subject’s retained notes.
- **Owner** — The member responsible for this work or channel.
- **Current comparison values** — The current target values supplied for comparison before acceptance of this proposal.

## States

### Proposed

The human has not accepted or dismissed this retained proposal; a failed application leaves it in this state.

### Accepted

The supported target write succeeded after human confirmation; the process remembers the accepted decision.

### Dismissed

The human dismissed this proposal; dismissal performs no target CRM write.
