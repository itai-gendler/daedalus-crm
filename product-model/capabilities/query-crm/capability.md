---
{
  "availability": [
    {
      "place": "crm-agent"
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
      "target": "src/lib/mcp/tools.ts"
    }
  ]
}
---

# Query Crm

The delegated MCP contract exposes fifteen enabled tools and whitelisted record/metric queries. It checks current token, enabled connection and active generating human; hosted mode and disabled supplier tool are rejected.
