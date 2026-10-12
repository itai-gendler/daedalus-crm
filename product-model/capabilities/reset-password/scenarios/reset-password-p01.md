---
{
  "kind": "primary",
  "routes": {
    "wp": "Web public",
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "The visitor invokes reset password for the case “Email code and new password”.",
      "kind": "actor",
      "entities": [],
      "actor": "visitor",
      "contexts": {
        "wp": {
          "place": "crm-web::public::password-recovery"
        },
        "dp": {
          "place": "crm-desktop::public::password-recovery"
        }
      }
    },
    {
      "text": "Email code and new password. A bounded expiring one-use email code authorizes password replacement. The send response is uniform; replacement invalidates older cloud sessions and devices.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "changes",
          "facts": [
            "Credentials",
            "Session cutoff"
          ]
        }
      ],
      "actor": "visitor",
      "contexts": {
        "wp": {
          "place": "crm-web::public::password-recovery"
        },
        "dp": {
          "place": "crm-desktop::public::password-recovery"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/login/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/signup/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/forgot/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/landing.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/route-memory.js"
    }
  ]
}
---

# Email code and new password

## Trigger

The visitor invokes reset password for the case “Email code and new password”.

## Outcome

Email code and new password. A bounded expiring one-use email code authorizes password replacement. The send response is uniform; replacement invalidates older cloud sessions and devices.
