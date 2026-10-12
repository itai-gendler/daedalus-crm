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
      "verb": "direct-source-for",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer",
      "verb": "attributed-to",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "channels"
}
---

# 渠道

A named active or inactive acquisition channel with a responsible member and direct/inherited customer attribution.

## Information kept

- **Name** — The displayed identity of this subject.
- **Phone** — The recorded phone value under the subject’s identity/validation rules.
- **Notes** — The subject’s retained notes.
- **Owner** — The member responsible for this work or channel.
- **Active** — The kept active flag, distinct from a session or a computed permission.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## States

### Active

The channel is available in active-channel choices.

### Inactive

The channel is excluded from active choices while existing attribution remains.
