---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "crm-account",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm::members"
        },
        {
          "place": "crm-web::public::login"
        },
        {
          "place": "crm-agent"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "holds",
          "entity": "crm-admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "crm-manager"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    },
    {
      "actors": [
        "crm-admin",
        "operator"
      ]
    },
    {
      "actors": [
        "crm-admin",
        "crm-manager",
        "crm-sales"
      ]
    },
    {
      "related": [
        {
          "verb": "publishes",
          "entity": "mcp-connection"
        },
        {
          "verb": "generated",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-admin"
        },
        {
          "verb": "connects",
          "entity": "ai-agent"
        }
      ],
      "when": [
        {
          "entity": "mcp-connection",
          "fact": "Enabled",
          "is": true
        }
      ],
      "configuredBy": "crm-account"
    },
    {
      "related": [
        {
          "verb": "publishes",
          "entity": "mcp-connection"
        },
        {
          "verb": "generated",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-manager"
        },
        {
          "verb": "connects",
          "entity": "ai-agent"
        }
      ],
      "when": [
        {
          "entity": "mcp-connection",
          "fact": "Enabled",
          "is": true
        }
      ],
      "configuredBy": "crm-account"
    },
    {
      "related": [
        {
          "verb": "publishes",
          "entity": "mcp-connection"
        },
        {
          "verb": "generated",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        },
        {
          "verb": "connects",
          "entity": "ai-agent"
        }
      ],
      "when": [
        {
          "entity": "mcp-connection",
          "fact": "Enabled",
          "is": true
        }
      ],
      "configuredBy": "crm-account"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/team-scope.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/mcp/tools.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/mcp/token.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/agent/tools.ts"
    }
  ]
}
---

# Only related CRM administrators, related sales managers, related salespeople, CRM administrators and operations staff, CRM administrators, sales managers and salespeople and related delegated MCP clients may read Crm Account

This Rule governs read operations on Crm Account at crm-web::crm::members, crm-web::public::login and crm-agent.

The selected operation can pass through any one of these grants:

- The CRM administrators reached through 系统管理员 / 老板 (holds).
- The sales managers reached through 销售主管 (holds).
- The salespeople reached through 销售 (holds).
- CRM administrators and operations staff.
- CRM administrators, sales managers and salespeople.

Every delegated grant starts at the governed record/book's actual publishing connection, reaches that connection's retained generating member and current CRM role, and ends at the external AI Agent connected by that member. The presented token must match this same book's current mcpToken; rotation/disable or an inactive generating member refuses. A roster account or a different book's connection cannot supply delegation. Hosted mode returns the implemented unavailable result.

The account configuration in these conjunctive grants is the actual retained Role assignment used by this invocation's query path. In native mode the wrapper's limiting identity is the running book's .cloud.json accountId mapped to acct_<accountId>, with the team-file and cached-role decision in the native-scope Rule; it is distinct from the token's generating member. The generating member supplies userId for explicit mine/recap/plan filters, while scoped wrapper operations independently apply the local limiting identity's customer/owner predicates. Neither an ADMIN token nor another owner's token bypasses that wrapper. Non-native queries have no native scope. Channels, unassigned contacts and roster queries have no added model owner filter. Whitelisted raw metric calls retain their actual raw-call scope; they do not acquire a fictitious generating-member owner predicate. Field/table/date/association whitelists, output bounds and explicit tool filters still apply; no grant permits CRM mutation or credential disclosure.


For this roster-read target, CRM Account in the target is the returned roster member, while the configured delegation account is the token generator. The generator must still be currently active, as the complete delegated decision above requires. It does not require every returned roster member to be active: list_users can explicitly include inactive members. The target Active fact is not used as a substitute for the generator identity check.
