---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "cloud-account",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::operations::accounts"
        },
        {
          "place": "crm-web::operations::account-record"
        },
        {
          "place": "crm-web::operations::overview"
        },
        {
          "place": "model-gateway"
        }
      ]
    }
  ],
  "permits": [
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

# Only configured operations staff or the bearer-bound model client read the selected Cloud Account

For console account lists, detail and overview, use the actual operations entry contract: an active cloud identity whose normalized contact is in this runtime’s OPS_ACCOUNTS, or the exact configured ADMIN_TOKEN. A CRM role alone supplies no operations access. The configuredBy grant refers only to these actual retained operator identities and console credential; it does not admit an unrelated runtime's configuration.

For gateway credit results, the presented nonrevoked device bearer resolves exactly one account, and only that account's balance, initial-gift explanation and account identifier are returned. Gateway deployment/configuration refusal remains 404 and failed device recognition remains 401. No independent Cloud Account Active check is added. The operations alternative does not turn the gateway into a console account lookup.

Credential lookup during sign-in is identity authentication, not a visitor read authorization policy or disclosure of account credentials. Those public-login reads are outside this Rule’s selector; their implemented credential validation remains in the sign-in cases.
