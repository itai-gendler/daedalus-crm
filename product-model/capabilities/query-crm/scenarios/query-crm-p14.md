---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “query_records”.",
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
      "text": "query_records validates one of nine whitelisted tables, supported fields/operators and the permitted one-hop relation. Rows default to twenty and clamp to fifty; grouped results cap at twenty while counts describe the full match. Invalid specifications return a corrective tool result. Shared masking and display labels apply; associated-contact counts may separately explain unassigned contacts.",
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

# query_records

## Trigger

The MCP client invokes query crm for the case “query_records”.

## Outcome

query_records validates one of nine whitelisted tables, supported fields/operators and the permitted one-hop relation. Rows default to twenty and clamp to fifty; grouped results cap at twenty while counts describe the full match. Invalid specifications return a corrective tool result. Shared masking and display labels apply; associated-contact counts may separately explain unassigned contacts.

## Edge cases

- Tables, fields, operators and the supported one-table relation are whitelisted; invalid specifications return a corrective tool result.
- Record results are capped at 50; grouping and counting have their own outcomes.
- Unassigned contacts are not rows in the associated-contact query; an unfiltered count can explicitly mention their separate number.
- Shared phone masking and configured status display labels apply to returned data.
