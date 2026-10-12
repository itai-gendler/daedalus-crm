---
{
  "kind": "primary",
  "routes": {
    "mcp": "MCP"
  },
  "steps": [
    {
      "text": "The MCP client invokes query crm for the case “get_customer”.",
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
      "text": "get_customer requires an identifier or name. Multiple name matches return up to six candidates without choosing one. A selected customer returns its profile, contacts, opportunities, signings, unfinished tasks, one plan and up to twenty recent follow-ups, retaining the original communication text.",
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
        },
        {
          "entity": "assigned-contact",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "WeChat",
            "Email",
            "Position",
            "Primary"
          ]
        },
        {
          "entity": "opportunity",
          "effect": "reads",
          "facts": [
            "Name",
            "Amount",
            "Currency",
            "Stage",
            "Status"
          ]
        },
        {
          "entity": "signing",
          "effect": "reads",
          "facts": [
            "Amount",
            "Precise amount",
            "Currency",
            "Signing date"
          ]
        },
        {
          "entity": "order",
          "effect": "reads",
          "facts": [
            "Number",
            "Payment information"
          ]
        },
        {
          "entity": "follow-up",
          "effect": "reads",
          "facts": [
            "Type",
            "Title",
            "Content",
            "Occurred time",
            "Duration",
            "Original text",
            "Recording member"
          ]
        },
        {
          "entity": "plan",
          "effect": "reads",
          "facts": [
            "Subject",
            "Planned time",
            "Method",
            "Done"
          ]
        },
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Title",
            "Due time",
            "Done"
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

# get_customer

## Trigger

The MCP client invokes query crm for the case “get_customer”.

## Outcome

get_customer requires an identifier or name. Multiple name matches return up to six candidates without choosing one. A selected customer returns its profile, contacts, opportunities, signings, unfinished tasks, one plan and up to twenty recent follow-ups, retaining the original communication text.
