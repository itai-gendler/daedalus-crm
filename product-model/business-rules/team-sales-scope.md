---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-customers"
    },
    {
      "type": "capability",
      "id": "browse-leads"
    },
    {
      "type": "capability",
      "id": "browse-opportunities"
    },
    {
      "type": "capability",
      "id": "browse-contacts"
    },
    {
      "type": "capability",
      "id": "browse-followups"
    },
    {
      "type": "capability",
      "id": "browse-schedules"
    },
    {
      "type": "capability",
      "id": "edit-customer"
    },
    {
      "type": "capability",
      "id": "edit-lead"
    },
    {
      "type": "capability",
      "id": "delete-customers"
    },
    {
      "type": "entity",
      "id": "assigned-contact"
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
      "id": "plan"
    },
    {
      "type": "entity",
      "id": "task"
    },
    {
      "type": "entity",
      "id": "unassigned-contact"
    },
    {
      "type": "capability",
      "id": "query-crm"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/prisma.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/me.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/cloud.ts"
    }
  ]
}
---

# Ordinary native SALES reads and changes retain their implemented scope

In native local mode the ordinary wrapper derives its scope from this running book, not from whichever human generated an MCP token. A .team.json file must exist in its CRM_DATA_DIR; read the current .cloud.json accountId and look up acct_<that accountId> in this book. Only a found row whose retained Role assignment is SALES supplies a limiting identity. Missing accountId, missing row, another role, or no team file produces no added scope; first-time lookup failure throws rather than silently opening scope. Keep the three-second cache: an expired cached value is used while a coalesced background lookup refreshes it, and failed refresh keeps the old value. Explicit role/team invalidation clears the cache. No immediate role-refresh guarantee is made.

For actual scoped model reads, updates and deletes, Customer must be sales-owned or channel-owned by that limiting identity, or currently pooled. Associated contacts, communications, opportunities, signings and orders follow their customer. Lead, Plan and Task also permit their own responsible/owning identity. Audit Log follows its author. Channels, unassigned contacts and the roster have no added model scope. These are request predicates, not separately kept Visible facts. Outside native local mode no such scope is added. Create/upsert, explicit 看全部, raw calls and real callback transaction delegates retain their actual boundaries; this decision never invents an extra direct-edit gate inside an unguarded callback.
