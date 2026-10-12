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
      "entity": "assigned-contact",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "opportunity",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "signing",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "order",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "follow-up",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "plan",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "task",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer",
      "verb": "refers",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "customers"
}
---

# 客户

The same addressable customer across general and trade work, with identity, attribution, ownership, pool presence and linked sales/communication work.

## Information kept

- **Name** — The displayed identity of this subject.
- **Phone** — The recorded phone value under the subject’s identity/validation rules.
- **WhatsApp** — The customer's recorded WhatsApp contact identifier.
- **WeChat** — The recorded WeChat contact identifier.
- **Country** — The customer's normalized country value.
- **Email** — The recorded email address; trade customer identity can use normalized email.
- **School/company** — The customer's school or company value under the applicable field wording.
- **Grade** — The customer's grade value in the applicable general CRM fields.
- **Major** — The customer's major or corresponding configured industry field.
- **Follow-up status** — The customer's fixed stored follow-up value, presented using configured wording.
- **Decision status** — The customer's fixed stored decision value, presented using configured wording.
- **Expected signing date** — The customer's expected signing date.
- **Sales owner** — The CRM member responsible for this customer's future sales work.
- **Direct source** — The customer's recorded direct source choice.
- **Direct channel** — The customer-selected channel for direct source attribution.
- **Referrer** — The customer who directly referred this customer.
- **Attributed channel** — The channel credited through the customer's resolved attribution chain.
- **Attributed customer** — The customer credited through the customer's resolved attribution chain.
- **Channel owner** — The CRM member credited for this customer's channel attribution.
- **Notes** — The subject’s retained notes.
- **Latest follow-up** — The derived most recent communication by occurred time, recalculated locally rather than synchronized as a conflicting field.
- **Pool state** — Whether a current pool entry exists; this is independent of sales ownership.
- **Pool entry** — The retained pool entry time and reason for the current pool presence.
- **Released by** — The member identified by a surviving manual pool entry; automatic release keeps no releasing member.
- **Claim time** — When the customer was last claimed; automatic pool timing can start from this claim.
- **Claimed by** — The member identified by the retained claim record.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## Stored vocabulary

Follow-up status: 待跟进, 跟进中, 已加微信, 已试听, 意向较高, 暂缓跟进, 已签约, 已流失. Decision status: 了解中, 对比中, 与家人商议, 等待预算, 已决定报名, 暂不考虑. Pool state is independent of ownership; release retains the owner. Configured display wording does not replace stored vocabulary.
