---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "cloud-account",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::public::registration"
        },
        {
          "place": "crm-desktop::public::login-or-registration"
        },
        {
          "place": "crm-web::crm::members"
        },
        {
          "place": "crm-web::operations::workspaces"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
      ]
    },
    {
      "actors": [
        "crm-admin"
      ]
    },
    {
      "actors": [
        "operator"
      ],
      "configuredBy": "service-config"
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

# Visitors register themselves, workspace administrators provision members and configured operators provision workspace accounts

The caller is bound to the actual selected creation operation. Public/native registration creates a new account from the submitted validated identity, under the shipped deployment/verification policy, consent and duplicate checks. It does not bind an already registered account to a new workspace.

Hosted member provisioning requires requireAdmin on the current nonshared workspace. The current workspace, new business member and submitted email form the exact binding; an existing cloud account is refused. Failure after cloud creation removes only that just-created account where the source cleanup runs. Selfhost member creation has no cloud-account creation.

Workspace provisioning requires the actual configured operations entry (active contact in OPS_ACCOUNTS or ADMIN_TOKEN). configuredBy refers to those retained identities/credential. It creates the specified workspace's new account and membership, returning the one-time initial password; it does not send a welcome email or adopt an unrelated identity.
