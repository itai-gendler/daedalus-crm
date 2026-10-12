---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "cloud-account",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::profile"
        },
        {
          "place": "crm-web::crm::profile"
        },
        {
          "place": "crm-web::operations::account-record"
        },
        {
          "place": "model-gateway"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "identifies",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "identifies",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-manager"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "identifies",
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
        "operator"
      ],
      "configuredBy": "service-config"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "logged-device"
        },
        {
          "verb": "uses",
          "entity": "model-client"
        }
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

# Only the related person, configured operator or bearer-bound model client changes the selected Cloud Account

Dispatch by the actual operation, not by an unrelated grant alternative. A current CRM profile identifies the caller’s mapped cloud account, and only its corresponding supported personal profile/password operation changes it. Current-password/code validation, shared-workspace refusal and session/device invalidation retain their source outcomes; this path does not administer another person's account.

Account-record operations require this runtime’s configured operations entry: active account/contact in OPS_ACCOUNTS or the exact ADMIN_TOKEN. Their supported changes are manual credits and test markers/history, not arbitrary credential or account-active edits. A CRM role alone supplies no operations authority. configuredBy is these retained operator identities and console credential.

Gateway accounting changes only the nonrevoked bearer device's own account allowance, after the actual body, attempt-limit and debit/reuse decisions. The separate gateway allowance Rule preserves refund sequencing, test-account bypass, failures and no-machine/no-daily-gift behavior. Other personal/operator alternatives do not authorize a gateway write.

Public recovery’s verification-code/password validation identifies the account for that recovery request; it is not a visitor account-administration permission. It remains outside this selector and inside the recovery contract.
