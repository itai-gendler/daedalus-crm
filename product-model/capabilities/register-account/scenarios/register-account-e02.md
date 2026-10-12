---
{
  "kind": "edge",
  "routes": {
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "The visitor invokes register account for the case “Desktop account created but automatic login fails”.",
      "kind": "actor",
      "entities": [],
      "actor": "visitor",
      "contexts": {
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
          "effect": "creates",
          "facts": [
            "Name",
            "Contact",
            "Active",
            "Credentials",
            "Session cutoff",
            "AI allowance",
            "Test marker",
            "Test history",
            "Registration time",
            "Initial gift received"
          ]
        }
      ],
      "actor": "visitor",
      "contexts": {
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

# Desktop account created but automatic login fails

## Trigger

The visitor invokes register account for the case “Desktop account created but automatic login fails”.

## Outcome

Verification delivery/network failure is exposed. On native account-created/auto-login failure the cloud account remains created and the user can retry login.
