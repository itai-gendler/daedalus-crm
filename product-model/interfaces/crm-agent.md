---
{
  "type": "agent",
  "actors": [
    "ai-agent"
  ],
  "languages": [
    "zh-CN"
  ],
  "entryPoints": [
    {
      "agent": "/api/mcp"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/mcp/token.ts"
    }
  ]
}
---

# Crm Agent

Delegated incoming read-only MCP tools.
