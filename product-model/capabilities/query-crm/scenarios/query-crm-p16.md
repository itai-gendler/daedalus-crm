---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “Whitelisted records/metric query boundaries”.",
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
      "text": "Unsupported tables, fields, operators, enum values and relation specifications produce corrective tool results rather than arbitrary database access. The record tool permits only its whitelisted one-hop relations, caps row/group output, and does not write records. The metric tool retains its separately implemented calculated-query contract.",
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

# Whitelisted records/metric query boundaries

## Trigger

The MCP client invokes query crm for the case “Whitelisted records/metric query boundaries”.

## Outcome

Unsupported tables, fields, operators, enum values and relation specifications produce corrective tool results rather than arbitrary database access. The record tool permits only its whitelisted one-hop relations, caps row/group output, and does not write records. The metric tool retains its separately implemented calculated-query contract.

## Edge cases

- Tables, fields, operators and the supported one-table relation are whitelisted; invalid specifications return a corrective tool result.
- Record results are capped at 50; grouping and counting have their own outcomes.
- Unassigned contacts are not rows in the associated-contact query; an unfiltered count can explicitly mention their separate number.
- Shared phone masking and configured status display labels apply to returned data.
