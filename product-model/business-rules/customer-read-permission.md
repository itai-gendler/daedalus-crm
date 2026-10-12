---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "customer",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-desktop::crm::customer-import"
        },
        {
          "place": "crm-desktop::crm::customer-record"
        },
        {
          "place": "crm-desktop::crm::customers"
        },
        {
          "place": "crm-desktop::crm::data"
        },
        {
          "place": "crm-desktop::crm::follow-ups"
        },
        {
          "place": "crm-desktop::crm::home"
        },
        {
          "place": "crm-desktop::crm::leads"
        },
        {
          "place": "crm-web::crm::customer-import"
        },
        {
          "place": "crm-web::crm::customer-record"
        },
        {
          "place": "crm-web::crm::customers"
        },
        {
          "place": "crm-web::crm::data"
        },
        {
          "place": "crm-web::crm::follow-ups"
        },
        {
          "place": "crm-web::crm::home"
        },
        {
          "place": "crm-web::crm::leads"
        },
        {
          "place": "crm-agent"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin",
        "crm-manager"
      ]
    },
    {
      "actors": [
        "crm-sales"
      ],
      "when": [
        {
          "entity": "service-config",
          "fact": "Hosting/native mode",
          "is-not": "desktop-local"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "sales-owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "channel-owns",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    },
    {
      "actors": [
        "crm-sales"
      ],
      "when": [
        {
          "fact": "Pool state",
          "is": "in"
        }
      ]
    },
    {
      "when": [
        {
          "entity": "desktop-config",
          "fact": "Current team binding",
          "absent": true
        }
      ],
      "related": [
        {
          "verb": "keeps",
          "entity": "desktop-config"
        },
        {
          "verb": "uses",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
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
        },
        {
          "entity": "crm-account",
          "fact": "Active",
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
        },
        {
          "entity": "crm-account",
          "fact": "Active",
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
        },
        {
          "entity": "crm-account",
          "fact": "Active",
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

# Only CRM administrators and sales managers, salespeople, related salespeople and related delegated MCP clients may read 客户

This Rule governs read operations on 客户 at crm-desktop::crm::customer-import, crm-desktop::crm::customer-record, crm-desktop::crm::customers, crm-desktop::crm::data, crm-desktop::crm::follow-ups, crm-desktop::crm::home, crm-desktop::crm::leads, crm-web::crm::customer-import, crm-web::crm::customer-record, crm-web::crm::customers, crm-web::crm::data, crm-web::crm::follow-ups, crm-web::crm::home, crm-web::crm::leads and crm-agent.

The selected operation can pass through any one of these grants:

- CRM administrators and sales managers.
- Salespeople, when Service Config.Hosting/native mode is not desktop-local.
- The salespeople reached through Crm Account (sales-owns) → 销售 (holds).
- The salespeople reached through Crm Account (channel-owns) → 销售 (holds).
- Salespeople, when 客户.Pool state is in.
- The salespeople reached through 桌面设置 (keeps) → Crm Account (uses) → 销售 (holds), when 桌面设置.Current team binding is absent.

Every delegated grant starts at the governed record/book's actual publishing connection, reaches that connection's retained generating member and current CRM role, and ends at the external AI Agent connected by that member. The presented token must match this same book's current mcpToken; rotation/disable or an inactive generating member refuses. A roster account or a different book's connection cannot supply delegation. Hosted mode returns the implemented unavailable result.

The account configuration in these conjunctive grants is the actual retained Role assignment used by this invocation's query path. In native mode the wrapper's limiting identity is the running book's .cloud.json accountId mapped to acct_<accountId>, with the team-file and cached-role decision in the native-scope Rule; it is distinct from the token's generating member. The generating member supplies userId for explicit mine/recap/plan filters, while scoped wrapper operations independently apply the local limiting identity's customer/owner predicates. Neither an ADMIN token nor another owner's token bypasses that wrapper. Non-native queries have no native scope. Channels, unassigned contacts and roster queries have no added model owner filter. Whitelisted raw metric calls retain their actual raw-call scope; they do not acquire a fictitious generating-member owner predicate. Field/table/date/association whitelists, output bounds and explicit tool filters still apply; no grant permits CRM mutation or credential disclosure.
