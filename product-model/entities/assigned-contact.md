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
      "verb": "cited-in",
      "cardinality": "one-to-many"
    }
  ]
}
---

# 客户联系人

A contact associated with a current customer and optionally cited by communications. Its Primary flag belongs to this association.

## Information kept

- **Name** — The displayed identity of this subject.
- **Phone** — The recorded phone value under the subject’s identity/validation rules.
- **WeChat** — The recorded WeChat contact identifier.
- **Email** — The recorded email address; trade customer identity can use normalized email.
- **Position** — The contact's recorded position or relationship to the customer.
- **Notes** — The subject’s retained notes.
- **Primary** — Whether this is the customer's designated primary contact.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.
