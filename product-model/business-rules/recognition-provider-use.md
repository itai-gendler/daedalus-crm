---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "service-config",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm::customer-import"
        },
        {
          "place": "crm-desktop::crm::customer-import"
        }
      ],
      "facts": [
        "Judgment credential"
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
      "configuredBy": "ai-config"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/customers/ai.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/jev/settings.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/jev/client.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/gateway/v1/systemone/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/device-token.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ai-quota.ts"
    }
  ]
}
---

# Explicit column recognition uses only this book's enabled recognition configuration

The human grant binds the actual requireUser account and import book. That book's retained AI Config Recognition enabled must be explicitly true (missing is off), a judgment connection must be available, and the current workspace must not be the shared trial workspace. The human explicitly requests recognition; an empty question set performs no provider call. Disabling or unavailable configuration returns null and preserves manual/rule mappings. No additional permission to inspect this configuration is invented.

Connection selection first uses this runtime's JEV_API_KEY and configured/default judgment destination when present. Otherwise native local mode uses this book's actual retained cloud device credential to the judgment relay; another book's credential does not qualify. The relay requires multi-tenant mode and its own JEV key (404 otherwise), recognizes the presented nonrevoked device (401 otherwise), applies its separate account-keyed rolling attempt window (429), the 256-KiB text bound (413), JSON/questions validation (400), and its fixed model. It does not read Cloud Account Active, generative balance or the remote book's assist setting, and does not authenticate a human import action. Those relay checks are internal transport checks, not an additional supported public interface or proof that every raw caller completed human confirmation.

Use the actual selected runtime's judgment key only outbound. The direct client has its eight-second timeout and one retry; relay timeout, provider errors or unusable answers fall back through the client to no usable recognition. No generative credits are debited and no credential is disclosed. Manual preview choices and late-result handling remain independent of provider success.
