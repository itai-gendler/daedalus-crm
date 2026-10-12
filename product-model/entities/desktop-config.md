---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/main.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/route-memory.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/reminders.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/updater.js"
    }
  ],
  "relations": [
    {
      "entity": "backup",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "lead",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "assigned-contact",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "unassigned-contact",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "opportunity",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "signing",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "order",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "follow-up",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "plan",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "task",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "channel",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "supplier",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "conversation",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "import-batch",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "audit-log",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "business-config",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "ai-config",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "mcp-connection",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "crm-account",
      "verb": "keeps",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "desktop"
}
---

# 桌面设置

The actual native client/book’s connection mode, identity/team binding, remembered route, preferences, cursors and update state.

## Information kept

- **Data mode** — The retained Local or Server native connection mode.
- **Server address** — The chosen remote site's address used by native server mode.
- **Data location** — The directory holding the current account-owned local book.
- **Account binding** — The cloud identity whose account-owned local book this native client opens.
- **Current team binding** — The native client/book’s actual current team association.
- **Remembered route** — The last supported working route retained for this account's local book.
- **Reminder preferences** — The retained controls for due notices, daily summaries and reminder timing.
- **Reminder cursor** — The latest due-reminder position already processed by the native client.
- **Operations cursor** — The latest native operations-feed position already processed.
- **Update state** — The native update's current checking, downloading, ready or error state.
- **Update version/method** — The selected update version and whole-package or qualified delta method.
- **Client version** — The native application version reported for this client or device.

## States

### Local

The native client works in the currently bound account's local book.

### Server

The native client opens the chosen remote site; this does not establish remote interface parity.
