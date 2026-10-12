---
{
  "availability": [
    {
      "place": "crm-desktop::crm"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/client.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/sync-relay.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/sync-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/device-token.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/desktop/sync/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/sync.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/local.ts"
    }
  ],
  "domain": "team"
}
---

# Sync Team

Prepares the currently bound local book, pushes then pulls under each relay request’s device/account/team checks, and applies returned field-clock/tombstone batches. Explicit and unattended rounds preserve their actual timing, key validation, partial outcomes and bookkeeping; returned-batch replay does not continuously revalidate membership or activation.
