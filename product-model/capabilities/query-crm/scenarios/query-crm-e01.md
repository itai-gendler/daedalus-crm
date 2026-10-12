---
{
  "kind": "edge",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “Empty/bounded/ambiguous/invalid query”.",
      "kind": "actor",
      "entities": [],
      "actor": "ai-agent",
      "contexts": {
        "mcp": {
          "place": "crm-agent"
        }
      }
    },
    {
      "text": "No matching records produce an empty result. A bounded result retains its limit and does not claim the omitted records are absent.",
      "kind": "product",
      "entities": [],
      "actor": "ai-agent",
      "contexts": {
        "mcp": {
          "place": "crm-agent"
        }
      }
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
      "target": "src/lib/agent/tools.ts#TOOLS"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/agent/query.ts"
    }
  ]
}
---

# Empty/bounded/ambiguous/invalid query

## Trigger

The MCP client invokes query crm for the case “Empty/bounded/ambiguous/invalid query”.

## Outcome

No matching records produce an empty result. A bounded result retains its limit and does not claim the omitted records are absent.
