---
{
  "availability": [
    {
      "place": "model-gateway"
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
      "target": "src/lib/tenant/credits.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/gateway/v1/models/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/gateway/v1/credits/route.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/gateway/v1/chat/completions/route.ts"
    }
  ]
}
---

# Complete Model

Supports nonstreaming tools or streaming without executing CRM writes. Limits: 30 per five minutes, first 20 question calls reuse charging, derived first-two-message identity in a 15-minute bucket or per-request fallback, 64 tools/200,000 serialized characters, output 1–8,000 and temperature 0–2. Unlisted model falls back; latest-request sequencing controls refunds.
