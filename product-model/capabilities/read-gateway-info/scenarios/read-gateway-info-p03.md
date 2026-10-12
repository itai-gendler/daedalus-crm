---
{
  "kind": "primary",
  "routes": {
    "gateway": "Model gateway"
  },
  "steps": [
    {
      "text": "The model client invokes read gateway info for the case “Refresh requesting device metadata from supplied headers”.",
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
      "text": "On the credits endpoint, recognized platform, architecture and client-version headers refresh the requesting device’s retained descriptors when different. An unknown platform skips this refresh; invalid optional architecture/version becomes null. Unchanged values skip writing and bookkeeping failures are best effort. Device recognition separately throttles last-use recording to five minutes.",
      "kind": "product",
      "entities": [
        {
          "entity": "logged-device",
          "effect": "changes",
          "facts": [
            "Platform",
            "Architecture",
            "Client version",
            "Last use"
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

# Refresh requesting device metadata from supplied headers

## Trigger

The model client invokes read gateway info for the case “Refresh requesting device metadata from supplied headers”.

## Outcome

On the credits endpoint, recognized platform, architecture and client-version headers refresh the requesting device’s retained descriptors when different. An unknown platform skips this refresh; invalid optional architecture/version becomes null. Unchanged values skip writing and bookkeeping failures are best effort. Device recognition separately throttles last-use recording to five minutes.
