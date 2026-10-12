---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “list_contracts”.",
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
      "text": "list_contracts returns up to thirty recent signings with the full match count and full amounts separated by currency. Inclusive date bounds normalize a reversed range. Frozen signing ownership falls back to current customer ownership; the result does not convert currencies.",
      "kind": "product",
      "entities": [
        {
          "entity": "signing",
          "effect": "reads",
          "facts": [
            "Amount",
            "Precise amount",
            "Currency",
            "Signing date",
            "Frozen sales owner",
            "Frozen channel owner"
          ]
        },
        {
          "entity": "mcp-connection",
          "effect": "reads",
          "facts": [
            "Enabled",
            "Generating member"
          ]
        }
      ],
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

# list_contracts

## Trigger

The MCP client invokes query crm for the case “list_contracts”.

## Outcome

list_contracts returns up to thirty recent signings with the full match count and full amounts separated by currency. Inclusive date bounds normalize a reversed range. Frozen signing ownership falls back to current customer ownership; the result does not convert currencies.
