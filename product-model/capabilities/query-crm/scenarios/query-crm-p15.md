---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “search_followups”.",
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
      "text": "search_followups requires a keyword, expands its supported synonyms and returns up to fifteen recent matches plus the full count. A positive day window caps at 365; the optional own-member filter uses the generating member. Returned content truncates to two hundred characters.",
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

# search_followups

## Trigger

The MCP client invokes query crm for the case “search_followups”.

## Outcome

search_followups requires a keyword, expands its supported synonyms and returns up to fifteen recent matches plus the full count. A positive day window caps at 365; the optional own-member filter uses the generating member. Returned content truncates to two hundred characters.
