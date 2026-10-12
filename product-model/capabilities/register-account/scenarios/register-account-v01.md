---
{
  "kind": "validation",
  "routes": {
    "wp": "Web public",
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "The visitor invokes register account for the case “Email/password/consent/duplicate/deployment rejection”.",
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
      "text": "The submitted request reaches this validation boundary: Email/password/consent/duplicate/deployment rejection.",
      "kind": "condition",
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
      "text": "Malformed email, unacceptable password, missing consent, duplicate account or an unavailable registration deployment returns the registration refusal without creating the requested account.",
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

# Email/password/consent/duplicate/deployment rejection

## Trigger

The visitor invokes register account for the case “Email/password/consent/duplicate/deployment rejection”.

## Outcome

Malformed email, unacceptable password, missing consent, duplicate account or an unavailable registration deployment returns the registration refusal without creating the requested account.
