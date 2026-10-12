---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “list_leads”.",
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
      "text": "list_leads returns up to thirty Leads with a full match count and supported keyword, status and source filters. Returned phones are masked. A converted-status filter tests the status value; it does not infer conversion from the customer association.",
      "kind": "product",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": [
            "Name",
            "Contact",
            "Industry",
            "Phone",
            "Email",
            "Status",
            "Source",
            "Responsible member",
            "Notes",
            "Conversion time",
            "Converted customer",
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

# list_leads

## Trigger

The MCP client invokes query crm for the case “list_leads”.

## Outcome

list_leads returns up to thirty Leads with a full match count and supported keyword, status and source filters. Returned phones are masked. A converted-status filter tests the status value; it does not infer conversion from the customer association.
