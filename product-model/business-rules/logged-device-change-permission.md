---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "logged-device",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-desktop::crm::profile"
        },
        {
          "place": "crm-web::crm::password"
        },
        {
          "place": "crm-web::crm::profile"
        },
        {
          "place": "model-gateway"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "cloud-account"
        },
        {
          "verb": "identifies",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "cloud-account"
        },
        {
          "verb": "identifies",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-manager"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "cloud-account"
        },
        {
          "verb": "identifies",
          "entity": "crm-account"
        },
        {
          "verb": "holds",
          "entity": "crm-sales"
        }
      ]
    },
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
      "target": "src/app/(app)/settings/actions.ts"
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

# Only the mapped owner or bearer-bound model client changes its Logged Device

Personal revocation resolves the caller’s actual mapped cloud account and requires the submitted device to belong to that account; it never revokes another account’s device. Native password/sign-out branches bind to the current .cloud.json/device, and cloud invalidation retains the source’s local-exit and later-check behavior.

The gateway alternative binds to the exact nonrevoked bearer device. It permits only recognition last-use bookkeeping and the credits route’s normalized platform/architecture/version refresh; it grants no device name change or arbitrary revocation. Public recovery credential validation remains its separate identity contract, not a visitor device-administration permission.
