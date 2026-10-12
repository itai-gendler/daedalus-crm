---
{
  "kind": "primary",
  "routes": {
    "wp": "Web public",
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "The visitor invokes read legal for the case “Privacy”.",
      "kind": "actor",
      "entities": [],
      "actor": "visitor",
      "contexts": {
        "wp": {
          "place": "crm-web::public::legal"
        },
        "dp": {
          "place": "crm-desktop::public::login-or-registration"
        }
      }
    },
    {
      "text": "Privacy. Displays the selected terms or privacy text; native public flows open the same published legal text.",
      "kind": "product",
      "entities": [],
      "actor": "visitor",
      "contexts": {
        "wp": {
          "place": "crm-web::public::legal"
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

# Privacy

## Trigger

The visitor invokes read legal for the case “Privacy”.

## Outcome

Privacy. Displays the selected terms or privacy text; native public flows open the same published legal text.
