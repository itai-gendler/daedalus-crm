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
  ]
}
---

# 跟进记录

A recorded customer communication, optionally associated with a contact, opportunity or order, retaining the bounded original source and recording member.

## Information kept

- **Type** — The communication kind, such as its selected method of contact.
- **Title** — The retained title used for this account, conversation, communication or task.
- **Status** — The subject's recorded status vocabulary described in its states or kept vocabulary.
- **Participants** — The recorded participants of the communication.
- **Content** — The communication text to retain or, for a draft, proposed for review.
- **Occurred time** — When the communication took place.
- **Duration** — The recorded or proposed duration of the communication.
- **Due time** — The task deadline or communication due time, where supplied.
- **Original text** — The original communication source text, bounded to 5,000 characters; normal editing does not replace it.
- **Recording member** — The CRM member recorded as author of the communication.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

- **Customer** — The current customer whose communication this is.
- **Contact** — The optional customer contact associated with this communication.
- **Opportunity** — The optional opportunity associated with this communication.
- **Order** — The optional order association, retaining an older node association when unchanged.

## States

### Recorded

The communication and its applicable original text/associations are retained.
