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
      "verb": "can-recover",
      "cardinality": "one-to-many"
    }
  ]
}
---

# 未关联联系人

An addressable detached contact retaining former customer context and recoverable communication links. It can be edited, deleted, reassociated or restored independently.

## Information kept

- **Name** — The displayed identity of this subject.
- **Phone** — The recorded phone value under the subject’s identity/validation rules.
- **WeChat** — The recorded WeChat contact identifier.
- **Email** — The recorded email address; trade customer identity can use normalized email.
- **Position** — The contact's recorded position or relationship to the customer.
- **Notes** — The subject’s retained notes.
- **Former customer** — The original customer association retained after detaching the contact.
- **Former customer name** — The former customer's retained display name, even if that customer disappears.
- **Recoverable follow-up links** — The former communication associations retained for restoration when their links are still null.
- **Detach time** — When the contact was moved out of its former customer.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## States

### Unassigned

The contact is outside a current customer while retaining former context and eligible links.
