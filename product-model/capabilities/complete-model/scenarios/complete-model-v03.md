---
{
  "kind": "validation",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes complete model for the case “Gateway unavailable or invalid/revoked device identity”.",
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
      "text": "The submitted request reaches this validation boundary: Gateway unavailable or invalid/revoked device identity.",
      "kind": "condition",
      "entities": [],
      "actor": "model-client",
      "contexts": {
        "gateway": {
          "place": "model-gateway"
        }
      }
    },
    {
      "text": "A gateway without usable hosted configuration returns 404; an invalid or revoked device bearer returns 401. No completion is forwarded. Account inactivity is not an independent device-authentication check on this route.",
      "kind": "product",
      "entities": [],
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

# Gateway unavailable or invalid/revoked device identity

## Trigger

The model client invokes complete model for the case “Gateway unavailable or invalid/revoked device identity”.

## Outcome

A gateway without usable hosted configuration returns 404; an invalid or revoked device bearer returns 401. No completion is forwarded. Cloud Account Active is not an independent device-authentication check on this route.
