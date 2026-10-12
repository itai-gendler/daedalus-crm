---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “list_orders”.",
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
      "text": "list_orders returns up to thirty lightweight orders and a full match count, with number, customer, amount/currency, payment, supplier, confirmation and owner summaries. The disabled full-node feature makes the late-only option ineffective; this tool does not expose the dormant twelve-node workflow.",
      "kind": "product",
      "entities": [
        {
          "entity": "order",
          "effect": "reads",
          "facts": [
            "Number",
            "Amount",
            "Currency",
            "Payment information",
            "Supplier information",
            "Confirmation time",
            "Owner"
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

# list_orders

## Trigger

The MCP client invokes query crm for the case “list_orders”.

## Outcome

list_orders returns up to thirty lightweight orders and a full match count, with number, customer, amount/currency, payment, supplier, confirmation and owner summaries. The disabled full-node feature makes the late-only option ineffective; this tool does not expose the dormant twelve-node workflow.
