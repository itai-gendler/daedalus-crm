---
{
  "kind": "edge",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes complete model for the case “Malformed upstream JSON refunds”.",
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
      "text": "For this ordinary fresh question, accounting debits one call before provider forwarding. Receipt bookkeeping failure can leave this debit committed.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "changes",
          "facts": [
            "AI allowance"
          ]
        }
      ],
      "actor": "model-client",
      "contexts": {
        "gateway": {
          "place": "model-gateway"
        }
      }
    },
    {
      "text": "A nonstreaming 200 response that cannot parse as JSON returns 502 and attempts the qualifying refund. The actual latest-sequence and one-refund receipt checks still apply; failed refund bookkeeping can retain the debit.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "changes",
          "facts": [
            "AI allowance"
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

# Malformed upstream JSON refunds

## Trigger

The model client invokes complete model for the case “Malformed upstream JSON refunds”.

## Outcome

A nonstreaming 200 response that cannot parse as JSON returns 502 and attempts the qualifying refund. The actual latest-sequence and one-refund receipt checks still apply; failed refund bookkeeping can retain the debit.
