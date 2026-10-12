---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "crm-account",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm::password"
        },
        {
          "place": "crm-web::crm::profile"
        },
        {
          "place": "crm-desktop::crm::profile"
        }
      ],
      "facts": [
        "Credentials"
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
      ],
      "configuredBy": "service-config"
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "crm-manager"
        }
      ],
      "configuredBy": "service-config"
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
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
    }
  ]
}
---

# Only related CRM administrators, related sales managers and related salespeople may change Crm Account

The configuredBy Entity is this runtime’s actual retained Shared workspace address and deployment configuration. 当前是共享区 returns false outside multi-tenant mode; in hosted mode it resolves the current tenant and reads that exact Workspace address/slug. Only a nonempty configured SHARED_WORKSPACE matching that slug makes it shared. A missing tenant or missing workspace row yields false for this predicate, while the operation’s independent identity/tenant guards still run. Presence of SHARED_WORKSPACE alone does not close a private workspace. No cached Allowed flag or arbitrary other workspace supplies this decision.

The related path binds the password operation to the actual current member and its hosted account link. Shared current workspace refuses. Hosted missing account mapping, wrong current password, short or identical new password refuse before the supported write. Resolve the current workspace before changing the cloud password; invalidate old sessions and devices, then sign the caller’s replacement session. Selfhost changes its own business password. Native cloud-code actions obtain the account from the current .cloud.json, not a supplied account identifier.
