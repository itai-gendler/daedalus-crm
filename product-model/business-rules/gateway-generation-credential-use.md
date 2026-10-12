---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "service-config",
      "effect": "reads",
      "contexts": [
        {
          "place": "model-gateway"
        }
      ],
      "facts": [
        "Generation credential"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "governs",
          "entity": "cloud-account"
        },
        {
          "verb": "owns",
          "entity": "logged-device"
        },
        {
          "verb": "uses",
          "entity": "model-client"
        }
      ],
      "when": [
        {
          "entity": "logged-device",
          "fact": "Revocation",
          "absent": true
        },
        {
          "fact": "Generation credential",
          "present": true
        }
      ],
      "configuredBy": "service-config"
    }
  ],
  "references": [
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
      "target": "src/lib/gateway.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ai-quota.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/credits.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/test-accounts.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/gateway/v1/chat/completions/route.ts"
    }
  ]
}
---

# Only the bearer-bound model client may cause configured gateway credential use

The related path binds this request to the Logged Device recognized from the presented bearer and to that device's own Cloud Account. The configuration is the actual hosting runtime's generation provider/key/model choices; an unrelated device, account or runtime cannot supply it. The Product uses the key outbound and never discloses it to the client.

Hosting must be multi-tenant with a usable gateway configuration, otherwise 404. Device recognition checks the dk_ token hash and nonrevocation, otherwise 401; it does not independently read Cloud Account Active. Last-use bookkeeping is throttled to five minutes and is best effort. Successful authentication alone does not authorize forwarding.

For completion dispatch, parse JSON, derive the actual account/question identity, apply the 30-per-five-minute rolling attempt limit, and validate the supported message/tool body before debit or provider forwarding. A live question's first twenty calls can reuse the attempt/charge allowance; later calls use the ordinary checks. Missing explicit question identity derives from this account, the first two messages and a fifteen-minute bucket when possible, otherwise uses per-request charging. Invalid body returns 400; exhausted attempt window returns 429; insufficient ordinary balance returns 402. A currently marked test account or contact in the configured operations list bypasses debit/balance denial, with display 999, but does not bypass request validation or the attempt window. Failed test-status lookup uses ordinary accounting.

Only after the actual debit/reuse decision succeeds may the normalized request use the configured provider key. Model fallback, tool/message/character bounds, output and temperature clamps remain. The gateway executes no CRM tool writes. Provider/network errors, cancellation and malformed responses retain the dispatched refund decision described by the allowance Rule; they do not broaden credential use to other operations.
