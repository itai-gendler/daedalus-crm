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
      "entity": "customer",
      "verb": "converted-to",
      "cardinality": "one-to-one"
    }
  ],
  "domain": "leads"
}
---

# 线索

An addressable potential customer before customer-record work. Conversion status and the optional direct converted-customer association are separate facts.

## Information kept

- **Name** — The displayed identity of this subject.
- **Contact** — The recorded contact person or contact address for this identity.
- **Industry** — The lead's recorded industry value.
- **Phone** — The recorded phone value under the subject’s identity/validation rules.
- **Email** — The recorded email address; trade customer identity can use normalized email.
- **Status** — The subject's recorded status vocabulary described in its states or kept vocabulary.
- **Source** — The lead's recorded acquisition source.
- **Responsible member** — The CRM member responsible for future work on this lead.
- **Notes** — The subject’s retained notes.
- **Conversion time** — When this lead was converted or merged into customer work.
- **Converted customer** — The optional direct customer association recorded during conversion; it is independent of the lead's status.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## States

### 待跟进

The lead is recorded as awaiting follow-up.

### 跟进中

The lead is recorded as being followed up.

### 已转化

The lead is recorded converted; this status alone does not assert a direct customer link.

### 已放弃

The lead is recorded abandoned.
