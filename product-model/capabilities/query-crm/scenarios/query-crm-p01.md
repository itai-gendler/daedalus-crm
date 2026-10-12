---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “search_customers”.",
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
      "text": "search_customers requires at least one search condition and returns up to thirty matching customers plus the full match count. Expected-date queries sort ascending; otherwise latest follow-up sorts descending. A name miss can suggest matches from the other person tables rather than pretending a customer exists.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "WhatsApp",
            "WeChat",
            "Country",
            "Email",
            "School/company",
            "Grade",
            "Major",
            "Follow-up status",
            "Decision status",
            "Expected signing date",
            "Sales owner",
            "Direct source",
            "Direct channel",
            "Referrer",
            "Attributed channel",
            "Attributed customer",
            "Channel owner",
            "Notes",
            "Latest follow-up",
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by",
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

# search_customers

## Trigger

The MCP client invokes query crm for the case “search_customers”.

## Outcome

search_customers requires at least one search condition and returns up to thirty matching customers plus the full match count. Expected-date queries sort ascending; otherwise latest follow-up sorts descending. A name miss can suggest matches from the other person tables rather than pretending a customer exists.
