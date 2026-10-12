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
      "entity": "order",
      "verb": "has",
      "cardinality": "one-to-one"
    }
  ]
}
---

# 签约

A recorded financial registration for a customer, with precise money, currency and owners frozen for that registration. Eligible linked-opportunity restoration uses the retained preceding values.

## Information kept

- **Amount** — The retained amount in its currency, with the financial process’s validation.
- **Precise amount** — The signing's precise monetary value alongside its displayed amount.
- **Currency** — The retained currency; summaries do not combine unlike currencies.
- **Signing date** — The date of the recorded customer signing.
- **Notes** — The subject’s retained notes.
- **Frozen sales owner** — The sales owner captured for the signing rather than replaced by later customer reassignment.
- **Frozen channel owner** — The channel owner captured for the signing rather than replaced by later reassignment.
- **Prior linked opportunity stage/probability** — The preceding values used only for eligible linked-opportunity restoration.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## States

### Recorded

The customer signing is retained with its money, owners and optional linked work.
