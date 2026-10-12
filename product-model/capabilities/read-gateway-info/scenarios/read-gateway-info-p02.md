---
{
  "kind": "primary",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes read gateway info for the case “Read own balance and initial-gift explanation”.",
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
      "text": "The credits endpoint returns this device-bound account’s balance, initial-gift receipt explanation and account identifier. Daily gift fields remain 0 and null. Without a machine hash this endpoint grants no initial gift. Test accounts display 999 and unlimited status rather than their actual balance.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "reads",
          "facts": [
            "AI allowance",
            "Initial gift received",
            "Test marker"
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

# Read own balance and initial-gift explanation

## Trigger

The model client invokes read gateway info for the case “Read own balance and initial-gift explanation”.

## Outcome

The credits endpoint returns this device-bound account’s balance, initial-gift receipt explanation and account identifier. Daily gift fields remain 0 and null. Without a machine hash this endpoint grants no initial gift. Test accounts display 999 and unlimited status rather than their actual balance.
