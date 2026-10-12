---
{
  "kind": "edge",
  "routes": {
    "wp": "Web public",
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "The visitor invokes register account for the case “Code/network failure”.",
      "kind": "actor",
      "entities": [],
      "actor": "visitor",
      "contexts": {
        "wp": {
          "place": "crm-web::public::registration"
        },
        "dp": {
          "place": "crm-desktop::public::login-or-registration"
        }
      }
    },
    {
      "text": "Verification delivery/network failure is exposed. On native account-created/auto-login failure the cloud account remains created and the user can retry login.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "reads",
          "facts": [
            "Active",
            "Contact"
          ]
        }
      ],
      "actor": "visitor",
      "contexts": {
        "wp": {
          "place": "crm-web::public::registration"
        },
        "dp": {
          "place": "crm-desktop::public::login-or-registration"
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

# Code/network failure

## Trigger

The visitor invokes register account for the case “Code/network failure”.

## Outcome

Verification delivery/network failure is exposed. On native account-created/auto-login failure the cloud account remains created and the user can retry login.
