---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “list_users”.",
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
      "text": "list_users returns up to fifty member names, titles, roles and customer/channel counts, active by default with explicit inactive inclusion. It does not return member credentials.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "reads",
          "facts": [
            "Name",
            "Title",
            "Role assignment",
            "Active"
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
            "Sales owner"
          ]
        },
        {
          "entity": "channel",
          "effect": "reads",
          "facts": [
            "Owner"
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

# list_users

## Trigger

The MCP client invokes query crm for the case “list_users”.

## Outcome

list_users returns up to fifty member names, titles, roles and customer/channel counts, active by default with explicit inactive inclusion. It does not return member credentials.

## Edge cases

- Roster matching is bounded to 50 and excludes inactive members by default; includeInactive changes this filter.
- The result includes name/title/role/active and work counts, without login secrets or password disclosure.
