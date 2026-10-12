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

# Browse Opportunities

Shows list or pipeline, recent wins and per-currency summaries without summing unlike currencies. Bounded and empty results remain distinguishable.
