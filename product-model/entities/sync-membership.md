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
  "domain": "team",
  "relations": [
    {
      "entity": "crm-account",
      "verb": "identifies",
      "cardinality": "one-to-one"
    },
    {
      "entity": "desktop-config",
      "verb": "bound-to",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Sync Membership

One account’s team participation, role, device participation and departure. Leaving retains Left time rather than deleting the membership.

## Information kept

- **Member identity** — The cloud identity and reconciled CRM member identity participating in this team.
- **Role** — The membership vocabulary within the containing workspace or synchronization team.
- **Joined time** — When the account joined the containing workspace or team.
- **Left time** — The membership departure time; leaving is a change, not deletion.
- **Device participation** — The member's registered devices and key envelopes used to exchange shared team data.

## States

### Joined

The membership has no left time and participates under the containing team's current service conditions.

### Left

The member's left time is retained; its local retention and key consequences follow the leave/removal behavior.
