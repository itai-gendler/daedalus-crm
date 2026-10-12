---
{
  "acts": "external",
  "kind": "system",
  "relations": [
    {
      "entity": "logged-device",
      "verb": "uses",
      "cardinality": "many-to-many"
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
      "target": "src/app/api/gateway/v1/chat/completions/route.ts"
    }
  ]
}
---

# Model Client

A compatible client using the supported model-gateway subset with a logged-device bearer credential.
