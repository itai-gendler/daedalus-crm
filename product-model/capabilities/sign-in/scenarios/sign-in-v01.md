---
{
  "kind": "validation",
  "routes": {
    "wp": "Web public",
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "A CRM member invokes sign in for the case “Account/credential rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Account/credential rejection.",
      "kind": "condition",
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
      "text": "An absent, inactive or mismatched account/credential produces the login rejection; no CRM session or another person's local book is adopted.",
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

# Account/credential rejection

## Trigger

A CRM member invokes sign in for the case “Account/credential rejection”.

## Outcome

An absent, inactive or mismatched account/credential produces the login rejection; no CRM session or another person's local book is adopted.
