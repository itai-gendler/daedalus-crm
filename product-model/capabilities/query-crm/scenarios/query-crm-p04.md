---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “find_person”.",
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
      "text": "find_person searches the supported customer, channel, associated-contact, Lead and member tables and returns typed matches with identifying contact fields. It does not merge or rewrite those people.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "Email"
          ]
        },
        {
          "entity": "channel",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "Active"
          ]
        },
        {
          "entity": "assigned-contact",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "Email",
            "Position"
          ]
        },
        {
          "entity": "lead",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "Email",
            "Status",
            "Contact"
          ]
        },
        {
          "entity": "crm-account",
          "effect": "reads",
          "facts": [
            "Name",
            "Active",
            "Title",
            "Role assignment"
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

# find_person

## Trigger

The MCP client invokes query crm for the case “find_person”.

## Outcome

find_person searches the supported customer, channel, associated-contact, Lead and member tables and returns typed matches with identifying contact fields. It does not merge or rewrite those people.
