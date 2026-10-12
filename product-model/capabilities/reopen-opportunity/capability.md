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

# Reopen Opportunity

Reopens under the linked-order guard, or restores stage/probability from undo information. Winning-stage paths do not imply identical normalization.
