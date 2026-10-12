---
{
  "kind": "configuration",
  "of": "journey-scenario",
  "settings": [
    {
      "entity": "business-config",
      "fact": "Template"
    }
  ],
  "takesEffect": "The winning control uses the current Business Config when invoked; financial submission rereads the configuration through saveContract.",
  "stability": "General may mark won without financial registration or retain a win after registration failure. Trade cancellation preserves the preceding opportunity. An open continuation does not freeze the server template; registration uses its actual submission-time configuration.",
  "alternatives": [
    {
      "id": "winning-opportunity-general-signing",
      "selectedWhen": "General template uses the general signing continuation."
    },
    {
      "id": "winning-opportunity-trade-order",
      "selectedWhen": "Trade template uses the order-producing continuation."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/opportunities/OpportunitiesView.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/ContractForm.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    }
  ]
}
---

# Winning Registration Template

The existing configuration selects the supported actor input path described by these alternatives.
