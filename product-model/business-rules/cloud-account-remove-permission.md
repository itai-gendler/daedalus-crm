---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "cloud-account",
      "effect": "removes",
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
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ops-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/members.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/gateway-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/device-token.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/actions.ts"
    }
  ]
}
---

# Only the provisioning administrator causes cleanup of the newly created Cloud Account

This removal is the actual hosted member-provisioning cleanup, not an account-deletion product control. requireAdmin already identifies the current nonshared workspace. If creating its membership fails after creating a new cloud account, 配账号 attempts deletion of that exact newly created account and then rethrows. Cleanup failure is caught and can leave a created account without the intended membership. No manager, salesperson or operator acquires general cloud-account deletion authority from this Rule; existing accounts are never adopted and deleted as cleanup.
