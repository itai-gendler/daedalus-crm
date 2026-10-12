---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "prisma/control.prisma"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/accounts.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/credits.ts"
    }
  ],
  "relations": [
    {
      "entity": "logged-device",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "workspace-membership",
      "verb": "holds",
      "cardinality": "one-to-many"
    },
    {
      "entity": "sync-membership",
      "verb": "holds",
      "cardinality": "one-to-many"
    },
    {
      "entity": "gift-log",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "model-usage-log",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "workspace",
      "verb": "provisions",
      "cardinality": "one-to-many"
    },
    {
      "entity": "crm-account",
      "verb": "identifies",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Cloud Account

The cloud identity used for hosted membership, native login and device-bound model access. It owns device participation and retained credit/test history.

## Information kept

- **Name** — The displayed identity of this subject.
- **Contact** — The recorded contact person or contact address for this identity.
- **Active** — The kept active flag, distinct from a session or a computed permission.
- **Credentials** — The credential material in the applicable identity store; it is used for verification and is not disclosed as a stored password.
- **Session cutoff** — The cloud-account time before which existing sessions are invalid.
- **AI allowance** — The retained grant/usage accounting for this owner; compatibility test display 999 does not replace the real balance.
- **Test marker** — The account's current manual test marker, distinct from inherent configured-operator treatment.
- **Test history** — The retained history of manual test-marker changes.
- **Registration time** — When the cloud identity was registered.
- **Initial gift received** — Whether this account has received its one-time initial AI gift.
