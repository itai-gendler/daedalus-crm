---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "business-config",
      "fact": "Template"
    }
  ],
  "takesEffect": "The editor displays the current Business Config; saveContract rereads it when the existing signing is submitted.",
  "stability": "Existing order identity is retained. Submission-time template controls order-field handling and conditional older-signing backfill; an existing order still receives money/currency changes when switched back to General. No fixed opening-time template guarantee is made.",
  "alternatives": [
    {
      "id": "edit-signing-p01",
      "selectedWhen": "General template uses ordinary signing edits."
    },
    {
      "id": "edit-signing-p02",
      "selectedWhen": "Trade template offers supported order-information editing."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/[id]/ContractForm.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-contract.ts"
    }
  ]
}
---

# Signing Edit Template

General sales teams edit a signing's amount, date and currency; export (trade) teams also edit its order information. Each workspace's template picks the form its team uses.
