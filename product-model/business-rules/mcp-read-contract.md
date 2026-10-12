---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "query-crm"
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
      "id": "mcp-connection"
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
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/mcp/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/mcp/token.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/mcp/tools.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/agent/tools.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/agent/query.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    }
  ]
}
---

# Incoming MCP exposes only its enabled read contract

The incoming contract exposes fifteen enabled tools and the implemented whitelisted record-query subset. It checks the active generating human and supported deployment. Hosted entry is rejected, token rotation invalidates prior credentials, and disabled list_suppliers is not part of the promised contract.


The incoming credential checks its actual current book token and active generating member. Native model delegation uses the running book’s independent local identity/cache, while explicit own-member tool filters use the generator. Metric/raw query dispatch retains its implemented scope; it is not generalized to automatic delegate filtering or SQL writes. Roster inactive inclusion does not deactivate the generating identity check.
