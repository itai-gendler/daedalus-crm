---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "crm-account",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm::members"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-admin"
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

# Only CRM administrators may create Crm Account

The configuredBy Entity is this runtime’s actual retained Shared workspace address and deployment configuration. 当前是共享区 returns false outside multi-tenant mode; in hosted mode it resolves the current tenant and reads that exact Workspace address/slug. Only a nonempty configured SHARED_WORKSPACE matching that slug makes it shared. A missing tenant or missing workspace row yields false for this predicate, while the operation’s independent identity/tenant guards still run. Presence of SHARED_WORKSPACE alone does not close a private workspace. No cached Allowed flag or arbitrary other workspace supplies this decision.

requireAdmin requires the actual current role ADMIN and refuses the current shared workspace. Native startup/restoration and operations provisioning are separate dispatches, not this members control. Member input validation, duplicate email/account rejection, hosted account/membership/link creation and actual rollback boundaries remain in their scenarios.
