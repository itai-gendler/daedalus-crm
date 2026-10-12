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
      "target": "src/lib/tenant/sync-relay.ts"
    }
  ],
  "relations": [
    {
      "entity": "sync-membership",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "team"
}
---

# 同步团队

The native team and its shared-data service, invite/key generation and activation state. Each successful service activation replaces its activation time.

## Information kept

- **Name** — The displayed identity of this subject.
- **Active** — The kept active flag, distinct from a session or a computed permission.
- **Activation time** — When operations most recently activated the team; activation replaces this time.
- **Invite/key generation** — The current team invite and shared data-key generation, including device envelopes.
- **Creator** — The cloud identity that created the synchronization team.
- **Sync state** — The team's retained exchange state, including progress, errors and resume information.

## States

### Waiting

The team exists but operations has not yet activated synchronization.

### Active

Synchronization service is activated for this team, using its latest activation time.

### Suspended

Team service is inactive; push/pull stops without deleting members' local files.
