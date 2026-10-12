---
{
  "kind": "edge",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes read gateway info for the case “No daily gift and unknown machine grants no signup gift”.",
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
      "text": "The credits endpoint reports whether the initial gift was previously received. Because this route has no machine hash, it grants no signup gift and no daily gift; the retained allowance remains unchanged.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "reads",
          "facts": [
            "AI allowance",
            "Initial gift received"
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

# No daily gift and unknown machine grants no signup gift

## Trigger

The model client invokes read gateway info for the case “No daily gift and unknown machine grants no signup gift”.

## Outcome

The credits endpoint reports whether the initial gift was previously received. Because this route has no machine hash, it grants no signup gift and no daily gift; the retained allowance remains unchanged.
