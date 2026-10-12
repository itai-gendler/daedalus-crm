---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "crm-account",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm::profile"
        },
        {
          "place": "crm-desktop::crm::profile"
        }
      ],
      "facts": [
        "Name",
        "Title"
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

The related path binds the change to me.id, not a submitted person. Shared current workspace returns the shipped profile refusal before mutation. Empty/overlong name and overlong title retain their ordinary validation outcomes; unchanged fields succeed without a write. Supported name/title changes are audited without changing login or role.
