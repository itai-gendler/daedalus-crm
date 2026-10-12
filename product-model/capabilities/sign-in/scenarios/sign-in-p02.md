---
{
  "kind": "primary",
  "routes": {
    "wp": "Web public"
  },
  "steps": [
    {
      "text": "A CRM member invokes sign in for the case “Hosted membership enters workspace”.",
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
      "text": "Hosted membership enters workspace. Credentials are checked in the deployment identity store. Hosted membership selects the workspace; native cloud login selects only the account-owned local directory. Rejected or unavailable identity never adopts another account’s files.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "reads",
          "facts": [
            "Contact",
            "Credentials",
            "Active"
          ]
        },
        {
          "entity": "workspace-membership",
          "effect": "reads",
          "facts": [
            "Role"
          ]
        },
        {
          "entity": "workspace",
          "effect": "reads",
          "facts": [
            "Status",
            "Address/slug",
            "Trial expiry",
            "Paid expiry"
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

# Hosted membership enters workspace

## Trigger

A CRM member invokes sign in for the case “Hosted membership enters workspace”.

## Outcome

Hosted membership enters workspace. Credentials are checked in the deployment identity store. Hosted membership selects the workspace; native cloud login selects only the account-owned local directory. Rejected or unavailable identity never adopts another account’s files.
