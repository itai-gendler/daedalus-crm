---
{
  "kind": "validation",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes complete model for the case “Invalid body/messages/tools”.",
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
      "text": "The submitted request reaches this validation boundary: Invalid body/messages/tools.",
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
      "text": "Malformed JSON or an invalid message/tool body returns 400 before debit or forwarding. Device last-use recognition can already have been recorded best effort; this completion path does not refresh platform, architecture or client-version descriptors.",
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

# Invalid body/messages/tools

## Trigger

The model client invokes complete model for the case “Invalid body/messages/tools”.

## Outcome

Malformed JSON or an invalid message/tool body returns 400 before debit or forwarding. Device last-use recognition can already have been recorded best effort; this completion path does not refresh platform, architecture or client-version descriptors.
