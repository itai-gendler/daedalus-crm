---
{
  "kind": "edge",
  "routes": {
    "wp": "Web public",
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "The visitor invokes reset password for the case “Uniform send response/network failure”.",
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
      "text": "The dependency or network error is shown; the interface does not claim that the requested save completed.",
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

# Uniform send response/network failure

## Trigger

The visitor invokes reset password for the case “Uniform send response/network failure”.

## Outcome

The dependency or network error is shown; the interface does not claim that the requested save completed.
