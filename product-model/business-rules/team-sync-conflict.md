---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sync-team"
    },
    {
      "type": "entity",
      "id": "assigned-contact"
    },
    {
      "type": "entity",
      "id": "audit-log"
    },
    {
      "type": "entity",
      "id": "business-config"
    },
    {
      "type": "entity",
      "id": "channel"
    },
    {
      "type": "entity",
      "id": "crm-account"
    },
    {
      "type": "entity",
      "id": "customer"
    },
    {
      "type": "entity",
      "id": "follow-up"
    },
    {
      "type": "entity",
      "id": "lead"
    },
    {
      "type": "entity",
      "id": "opportunity"
    },
    {
      "type": "entity",
      "id": "order"
    },
    {
      "type": "entity",
      "id": "plan"
    },
    {
      "type": "entity",
      "id": "signing"
    },
    {
      "type": "entity",
      "id": "supplier"
    },
    {
      "type": "entity",
      "id": "sync-team"
    },
    {
      "type": "entity",
      "id": "task"
    },
    {
      "type": "entity",
      "id": "unassigned-contact"
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
  ]
}
---

# Synchronization retains its local preparation and partial replay outcomes

A bound native round prepares triggers and reads pending changes before relay membership/activation checks. Push precedes pull; each relay request checks the presented device's account and exact team membership, Active and applicable packet/key conditions. Applying an already returned batch does not recheck these relay predicates per row. Supported tables use field clocks, tombstones and conflict handling, with durable per-batch progress only while the same local team binding remains. Schema change retries once immediately; missing keys wait rather than count as corruption, while repeated other decryption failures skip after three attempts. Concurrent rounds coalesce and local writes can queue another; exit waits and blocks new rounds. Full shared-book transport does not promise separate per-salesperson encrypted copies. Settings share business only, excluding AI credentials, native preferences, conversations and import undo batches; passwords/roles do not synchronize and latest follow-up is derived locally.
