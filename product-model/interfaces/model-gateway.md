---
{
  "type": "api",
  "actors": [
    "model-client"
  ],
  "languages": [
    "zh-CN"
  ],
  "entryPoints": [
    {
      "api": "/api/gateway/v1/models"
    },
    {
      "api": "/api/gateway/v1/credits"
    },
    {
      "api": "/api/gateway/v1/chat/completions"
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

# Model Gateway

Model discovery, credits and the supported completion subset for compatible clients.
