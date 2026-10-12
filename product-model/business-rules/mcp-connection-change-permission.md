---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mcp-connection",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::ai-settings"
        },
        {
          "place": "crm-web::crm::ai-settings"
        }
      ],
      "facts": [
        "Enabled",
        "Address",
        "Credential",
        "Generating member",
        "Generation time"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin",
        "crm-manager",
        "crm-sales"
      ],
      "configuredBy": "service-config"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/shared-ws/current.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/shared-ws/config.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/resolve.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/mcp/token.ts"
    }
  ]
}
---

# Only the current administrator or native local member changes this book’s MCP connection

Use this runtime’s retained deployment configuration and the caller’s actual current role. Both enable/rotation and disable first requireUser, reject multiTenant unconditionally, and then require ADMIN or DESKTOP_LOCAL exactly "1". Being a private hosted workspace does not enable MCP. The check is not Shared workspace address absence.

The operation changes only the actual current book’s mcpToken setting. Rotation binds its generator to me.id and invalidates the old token; disable clears the current token. It does not produce a connection for another book, disclose another connection’s credential or gain CRM write access. The generating member’s active check and bearer matching belong to the incoming read contract.
