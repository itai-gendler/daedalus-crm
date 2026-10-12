---
{
  "kind": "validation",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “Token/generator/hosted/tool rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Token/generator/hosted/tool rejection.",
      "kind": "condition",
      "entities": [],
      "actor": "ai-agent",
      "contexts": {
        "mcp": {
          "place": "crm-agent"
        }
      }
    },
    {
      "text": "An invalid/disabled token, inactive generating member, unsupported hosted deployment or rejected tool request returns the MCP refusal without the requested CRM data or any CRM write.",
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

# Token/generator/hosted/tool rejection

## Trigger

The MCP client invokes query crm for the case “Token/generator/hosted/tool rejection”.

## Outcome

An invalid/disabled token, inactive generating member, unsupported hosted deployment or rejected tool request returns the MCP refusal without the requested CRM data or any CRM write.
