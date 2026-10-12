---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “list_channels”.",
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
      "text": "list_channels returns up to fifty channels, active by default, with optional inactive inclusion. It reports direct and inherited-chain customer counts and signing amounts separated by currency, retaining the channel distinction.",
      "kind": "product",
      "entities": [
        {
          "entity": "channel",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "Notes",
            "Owner",
            "Active",
            "Created time",
            "Last change"
          ]
        },
        {
          "entity": "mcp-connection",
          "effect": "reads",
          "facts": [
            "Enabled",
            "Generating member"
          ]
        },
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Name",
            "Direct channel",
            "Attributed channel"
          ]
        },
        {
          "entity": "signing",
          "effect": "reads",
          "facts": [
            "Amount",
            "Currency"
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

# list_channels

## Trigger

The MCP client invokes query crm for the case “list_channels”.

## Outcome

list_channels returns up to fifty channels, active by default, with optional inactive inclusion. It reports direct and inherited-chain customer counts and signing amounts separated by currency, retaining the channel distinction.
