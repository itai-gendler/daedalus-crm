---
{
  "kind": "validation",
  "routes": {
    "wp": "Web public",
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "The visitor invokes reset password for the case “Invalid/expired code, password, phone identity, or unavailable deployment”.",
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
      "text": "The submitted request reaches this validation boundary: Invalid/expired code, password, phone identity, or unavailable deployment.",
      "kind": "condition",
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
      "text": "An invalid or expired code, unacceptable password, unsupported phone identity or unavailable deployment prevents password replacement; an existing password is not reported changed.",
      "kind": "product",
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

# Invalid/expired code, password, phone identity, or unavailable deployment

## Trigger

The visitor invokes reset password for the case “Invalid/expired code, password, phone identity, or unavailable deployment”.

## Outcome

An invalid or expired code, unacceptable password, unsupported phone identity or unavailable deployment prevents password replacement; an existing password is not reported changed.
