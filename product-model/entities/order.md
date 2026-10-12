---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/schema.prisma"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    }
  ],
  "relations": [
    {
      "entity": "follow-up",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---

# 订单

An independently addressed lightweight trade order, optionally linked to signing/opportunity and associated communications. Supported money, supplier and payment information belong to this subject.

## Information kept

- **Number** — The order number used to identify the customer's trade order.
- **Amount** — The retained amount in its currency, with the financial process’s validation.
- **Currency** — The retained currency; summaries do not combine unlike currencies.
- **Payment information** — The lightweight order's retained payment details.
- **Supplier information** — The supplier details retained with the enabled lightweight trade order.
- **Trade terms** — The enabled trade order's delivery/trade terms.
- **Legacy deposits** — Older retained order-deposit information exposed where the lightweight order contract supports it.
- **Confirmation time** — The order's retained confirmation time, where present.
- **Notes** — The subject’s retained notes.
- **Owner** — The member responsible for this work or channel.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## States

### Recorded

The lightweight trade order is retained independently of its originating opportunity.
