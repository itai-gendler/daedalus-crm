---
{
  "kind": "primary",
  "routes": {
    "wp": "Web public",
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "The visitor invokes register account for the case “Registration without code”.",
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
      "text": "Registration without code. Email, password and consent are validated under the deployed signup and optional verification policy. Signup creates the cloud account without a workspace; native signup attempts automatic login afterward.",
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

# Registration without code

## Trigger

The visitor invokes register account for the case “Registration without code”.

## Outcome

Registration without code. Email, password and consent are validated under the deployed signup and optional verification policy. Signup creates the cloud account without a workspace; native signup attempts automatic login afterward.
