---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "logged-device",
      "effect": "changes",
      "contexts": [
        {
          "place": "model-gateway"
        }
      ],
      "facts": [
        "Platform",
        "Architecture",
        "Client version",
        "Last use"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "uses",
          "entity": "model-client"
        }
      ]
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
      "target": "src/lib/tenant/device-token.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/device-info.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/gateway/v1/credits/route.ts"
    }
  ]
}
---

# Only related model clients may change 登录设备

This Rule governs change operations on 登录设备 affecting Platform, Architecture, Client version and Last use at model-gateway.

The selected operation can pass through any one of these grants:

- The model clients reached through Model Client (uses).

Only credits dispatch applies supplied client descriptors to the device identified by this bearer. Unknown platform omits the whole descriptor update; supported architecture/version are normalized, invalid optional descriptors become null, unchanged values skip writing and persistence failure is best effort. Completion dispatch does not apply descriptor headers. Recognition may separately refresh Last use after its five-minute threshold.
