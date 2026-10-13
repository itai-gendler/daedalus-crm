---
{
  "kind": "primary",
  "routes": {
    "wp": "Web public"
  },
  "steps": [
    {
      "text": "A CRM member invokes sign in for the case “Selfhost credentials enter CRM”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wp": {
          "place": "crm-web::public::login"
        }
      }
    },
    {
      "text": "Selfhost credentials enter CRM. The login and password are checked against an active Crm Account in this deployment’s own store, and the member enters the CRM in a new session.",
      "kind": "product",
      "entities": [
        {
          "entity": "crm-account",
          "effect": "reads",
          "facts": [
            "Login",
            "Credentials",
            "Active"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "wp": {
          "place": "crm-web::public::login"
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

# Selfhost credentials enter CRM

## Trigger

A CRM member invokes sign in for the case “Selfhost credentials enter CRM”.

## Outcome

Selfhost credentials enter CRM. The login and password are checked against an active Crm Account in this deployment’s own store, and the member enters the CRM in a new session.
