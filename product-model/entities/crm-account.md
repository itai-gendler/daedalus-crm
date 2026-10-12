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
      "entity": "sync-team",
      "verb": "created",
      "cardinality": "one-to-many"
    },
    {
      "entity": "conversation",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "mcp-connection",
      "verb": "generated",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer",
      "verb": "sales-owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer",
      "verb": "channel-owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer",
      "verb": "released",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer",
      "verb": "claimed",
      "cardinality": "one-to-many"
    },
    {
      "entity": "lead",
      "verb": "responsible-for",
      "cardinality": "one-to-many"
    },
    {
      "entity": "channel",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "opportunity",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "plan",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "task",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "follow-up",
      "verb": "recorded",
      "cardinality": "one-to-many"
    },
    {
      "entity": "import-batch",
      "verb": "imported",
      "cardinality": "one-to-many"
    },
    {
      "entity": "audit-log",
      "verb": "authored",
      "cardinality": "one-to-many"
    },
    {
      "entity": "desktop-config",
      "verb": "uses",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Crm Account

The personal CRM identity behind a fixed CRM role, scoped to its book. Its profile and favorites stay with the same account when the person’s role changes.

## Information kept

- **Name** — The displayed identity of this subject.
- **Login** — The login identifier in the applicable CRM identity store; hosted login uses email while selfhost uses the normalized username.
- **Title** — The retained title used for this account, conversation, communication or task.
- **Role assignment** — The fixed ADMIN, MANAGER or SALES assignment; native team roles are locally reconciled from creator/member identity, rather than synchronized.
- **Active** — The kept active flag, distinct from a session or a computed permission.
- **Credentials** — The credential material in the applicable identity store; it is used for verification and is not disclosed as a stored password.
- **Favorites** — The current account’s ordered customer favorites, limited to eight.
- **Created time** — When this subject was created.
- **Last change** — The kept last modification time used by the applicable version/snapshot guard.

## States

### Active

The CRM account is active for the inspected identity and work contexts.

### Inactive

The CRM account is deactivated; retained historical authorship and performance remain.
