---
{
  "kind": "primary",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes complete model for the case “Stream completion”.",
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
      "text": "A valid streaming completion returns the upstream stream directly with streaming response headers. This path does not record token usage, and does not establish a later body-stream failure refund guarantee.",
      "kind": "product",
      "entities": [
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

# Stream completion

## Trigger

The model client invokes complete model for the case “Stream completion”.

## Outcome

A valid streaming completion returns the upstream stream directly with streaming response headers. This path does not record token usage, and does not establish a later body-stream failure refund guarantee.
