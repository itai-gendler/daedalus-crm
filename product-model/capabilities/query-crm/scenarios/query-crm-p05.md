---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “my_recap”.",
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
      "text": "my_recap defaults to seven days and clamps the requested window to 1–90 days. It returns full follow-up and distinct-customer counts plus signing and newly created customer counts, with bounded samples of fifty follow-ups, thirty signings and thirty customers. “My” filters use the token’s generating member; frozen signing ownership falls back to current ownership.",
      "kind": "product",
      "entities": [
        {
          "entity": "follow-up",
          "effect": "reads",
          "facts": [
            "Type",
            "Title",
            "Status",
            "Participants",
            "Content",
            "Occurred time",
            "Duration",
            "Due time",
            "Original text",
            "Recording member",
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
          "entity": "signing",
          "effect": "reads",
          "facts": [
            "Amount",
            "Currency",
            "Signing date",
            "Frozen sales owner"
          ]
        },
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Name",
            "Created time",
            "Sales owner"
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

# my_recap

## Trigger

The MCP client invokes query crm for the case “my_recap”.

## Outcome

my_recap defaults to seven days and clamps the requested window to 1–90 days. It returns full follow-up and distinct-customer counts plus signing and newly created customer counts, with bounded samples of fifty follow-ups, thirty signings and thirty customers. “My” filters use the token’s generating member; frozen signing ownership falls back to current ownership.
