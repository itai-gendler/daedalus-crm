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

# Create Opportunity

Validates name, positive/finite money where supplied, currency, stage and active owner in the selected customer context.
