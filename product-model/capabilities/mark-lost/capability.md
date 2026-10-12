---
{
  "availability": [
    {
      "place": "crm-web::crm"
    },
    {
      "place": "crm-desktop::crm"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/opportunities/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/order-contract.ts"
    }
  ],
  "domain": "opportunities"
}
---

# Mark Lost

Confirmed loss records LOST, closure time and the applicable stage/probability. Undo can use the prior values; no independent Lost reason fact is kept.
