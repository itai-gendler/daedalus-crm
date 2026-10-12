---
{
  "kind": "primary",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes complete model for the case “Question identifier reuses charge within step allowance”.",
      "kind": "actor",
      "entities": [],
      "actor": "model-client",
      "contexts": {
        "gateway": {
          "place": "model-gateway"
        }
      }
    },
    {
      "text": "A matching unrefunded question receipt below twenty calls increments its call count and forwards another completion without another debit. The count update is best effort; a refunded or exhausted receipt requires a new ordinary debit.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "reads",
          "facts": [
            "AI allowance",
            "Test marker"
          ]
        },
        {
          "entity": "service-config",
          "effect": "reads",
          "facts": [
            "Generation credential",
            "Generation model choices",
            "Generation provider address"
          ]
        }
      ],
      "actor": "model-client",
      "contexts": {
        "gateway": {
          "place": "model-gateway"
        }
      }
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

# Question identifier reuses charge within step allowance

## Trigger

The model client invokes complete model for the case “Question identifier reuses charge within step allowance”.

## Outcome

A matching unrefunded question receipt below twenty calls increments its call count and forwards another completion without another debit. The count update is best effort; a refunded or exhausted receipt requires a new ordinary debit.

## Edge cases

- The first 20 calls under the reused question identifier share the established charge; beyond that bound a new charge can be required.
- A missing question identifier uses the first two messages and 15-minute bucket where possible, otherwise each request is charged independently.
