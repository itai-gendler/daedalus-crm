---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "ai-config",
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
        "Provider address",
        "Model",
        "Choices",
        "Credential",
        "Credential hint",
        "Configuration source",
        "Recognition enabled"
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

# Only the current administrator or native local member may change local AI settings

The configuredBy Entity is this runtime’s actual retained Shared workspace address and deployment configuration. 当前是共享区 returns false outside multi-tenant mode; in hosted mode it resolves the current tenant and reads that exact Workspace address/slug. Only a nonempty configured SHARED_WORKSPACE matching that slug makes it shared. A missing tenant or missing workspace row yields false for this predicate, while the operation’s independent identity/tenant guards still run. Presence of SHARED_WORKSPACE alone does not close a private workspace. No cached Allowed flag or arbitrary other workspace supplies this decision.

For generation configuration save, clear and connection test, 能改本机设置 first requires the current user. DESKTOP_LOCAL exactly "1" returns that member directly for any fixed role; otherwise requireAdmin requires ADMIN and refuses the actual shared workspace. It does not prohibit every private workspace on a runtime that also has a shared workspace. The exact current book’s AI Config is changed or resolved for the test, not a team-shared credential or another book’s configuration.

Recognition-enabled changes use their own dispatch: ADMIN or DESKTOP_LOCAL is required, followed by the actual current shared-workspace refusal for every role. Missing recognition configuration defaults off. No computed Recognition available permission fact is invented. Provider address/model validation, retained-key versus supplied-key decisions and save/clear failure outcomes remain. Clearing interface settings does not guarantee removal of an environment fallback.
