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
      "entity": "signing",
      "verb": "linked-to",
      "cardinality": "one-to-many"
    },
    {
      "entity": "order",
      "verb": "linked-to",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "opportunities"
}
---

# 商机

A customer’s prospective financial outcome, with stage, probability and OPEN/WON/LOST status as distinct information.

## Information kept

- **Name** — The displayed identity of this subject.
- **Amount** — The retained amount in its currency, with the financial process’s validation.
- **Currency** — The retained currency; summaries do not combine unlike currencies.
- **Stage** — The opportunity's fixed stored pipeline stage, separate from OPEN/WON/LOST status.
- **Probability** — The opportunity's retained winning probability.
- **Status** — The subject's recorded status vocabulary described in its states or kept vocabulary.
- **Owner** — The member responsible for this work or channel.
- **Expected date** — The opportunity's expected closing date.
- **Notes** — The subject’s retained notes.
- **Closed time** — When the opportunity was recorded as closed.
- **Created time** — The recorded inquiry/creation time; the supported inquiry-date edit can backdate it within its date bounds.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## States

### OPEN

The opportunity is open for future sales work; its stage is kept separately.

### WON

The opportunity is recorded won; linked signing/order outcomes follow the particular winning path.

### LOST

The opportunity is recorded lost, with no separate lost-reason fact.

## Stage vocabulary

初步沟通, 需求确认, 方案报价, 谈判审核, 赢单成交. Stage and OPEN/WON/LOST status are distinct; a stage-only path can leave OPEN at the winning stage.
