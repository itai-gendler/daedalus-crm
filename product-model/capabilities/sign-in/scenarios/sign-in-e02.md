---
{
  "kind": "edge",
  "routes": {
    "wp": "Web public",
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "A CRM member invokes sign in for the case “Network/directory/local-identity failure”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wp": {
          "place": "crm-web::public::login"
        },
        "dp": {
          "place": "crm-desktop::public::login-or-registration"
        }
      }
    },
    {
      "text": "Cooldown remains enforced. A network, account directory or local identity error prevents completing login; another account’s data is not adopted.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wp": {
          "place": "crm-web::public::login"
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

# Network/directory/local-identity failure

## Trigger

A CRM member invokes sign in for the case “Network/directory/local-identity failure”.

## Outcome

Cooldown remains enforced. A network, account directory or local identity error prevents completing login; another account’s data is not adopted.
