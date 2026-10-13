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
  "takesEffect": "The current Business Config is read by the signing process and reread by saveContract when a registration is submitted.",
  "stability": "The form does not freeze the server template. The submission-time template determines whether the new signing creates a lightweight order, including calls with no order fields; saved financial records retain their actual history.",
  "alternatives": [
    {
      "id": "register-signing-p01",
      "selectedWhen": "General template collects signing money/date/currency."
    },
    {
      "id": "register-signing-p02",
      "selectedWhen": "Trade template also collects supported order information."
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

# Signing Registration Template

General sales teams record a signing with its amount, date and currency; export (trade) teams also record order information, which creates a lightweight order. Each workspace's template picks the form its team uses.
