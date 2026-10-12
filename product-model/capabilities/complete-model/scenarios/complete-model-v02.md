---
{
  "kind": "validation",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes complete model for the case “Rate or allowance denial”.",
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
      "text": "The submitted request reaches this validation boundary: Rate or allowance denial.",
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
      "text": "An exhausted rolling attempt window returns 429 before debit or forwarding. An ordinary insufficient balance returns 402 after the rejected increment is rolled back; the completion is not forwarded. A currently designated test account bypasses balance debit, while remaining subject to request validation and the attempt window.",
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

# Rate or allowance denial

## Trigger

The model client invokes complete model for the case “Rate or allowance denial”.

## Outcome

An exhausted rolling attempt window returns 429 before debit or forwarding. An ordinary insufficient balance returns 402 after the rejected increment is rolled back; the completion is not forwarded. A currently designated test account bypasses balance debit, while remaining subject to request validation and the attempt window.
