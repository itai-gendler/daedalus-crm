---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "cloud-account",
      "effect": "changes",
      "contexts": [
        {
          "place": "model-gateway"
        }
      ],
      "facts": [
        "AI allowance"
      ]
    }
  ],
  "permits": [
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
      ],
      "configuredBy": "cloud-account"
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

# Only the bound model client's actual account accounting decision changes its AI allowance

The presented bearer identifies the exact nonrevoked Logged Device and its account. Use that account's retained allowance and Test marker, with this runtime's configured operations identities; another account's balance or test mark cannot authorize this request. Recognition does not add a Cloud Account Active predicate.

Completion validates the body and rolling attempt gate before accounting. A current test account, including a configured operations contact, performs no debit or charge-receipt mutation; display 999 is not a balance write. Ordinary requests debit before forwarding only when balance remains, returning the implemented 402 otherwise. A matching unrefunded question receipt with fewer than twenty calls reuses its charge and increments its count; refunded/exhausted receipts or no question identity use the implemented new-debit path. Receipt lookup failure falls back to ordinary per-request charging; receipt-write/concurrent uniqueness failure can leave an additional committed debit. No transactional exactly-once charging guarantee is made.

Refund only for the actual qualifying dispatched result: network/timeout, upstream 5xx/429/408/401/402/403/404, nonstreaming malformed JSON, or the implemented abandonment path. Other upstream request failures remain charged. With a question identity only the latest request sequence may refund, and the unrefunded receipt update gates restoring a credit; with no identity it restores the actual debit without receipt idempotence. A reused charge can be refunded when that question's newest request fails. Accounting failure can retain the debit. Successful streaming bypasses ordinary token-usage recording. Gateway-info reads award no daily gift and, without a machine identity, no initial gift. These grants do not permit manual grants, other-account mutations or unrelated allowance changes.
