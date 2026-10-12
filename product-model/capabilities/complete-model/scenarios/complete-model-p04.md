---
{
  "kind": "primary",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes complete model for the case “Unlisted model falls back and output limits clamp”.",
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
      "text": "An unlisted model uses the configured default. Output tokens clamp to 1–8,000 and temperature to 0–2; normalized messages and tools are forwarded. Tools are limited to 64 and 200,000 serialized characters.",
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

# Unlisted model falls back and output limits clamp

## Trigger

The model client invokes complete model for the case “Unlisted model falls back and output limits clamp”.

## Outcome

An unlisted model uses the configured default. Output tokens clamp to 1–8,000 and temperature to 0–2; normalized messages and tools are forwarded. Tools are limited to 64 and 200,000 serialized characters.
