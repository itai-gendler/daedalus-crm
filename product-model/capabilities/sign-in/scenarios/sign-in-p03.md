---
{
  "kind": "primary",
  "routes": {
    "dp": "Native public"
  },
  "steps": [
    {
      "text": "A CRM member invokes sign in for the case “Desktop cloud login switches owned data”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "dp": {
          "place": "crm-desktop::public::login-or-registration"
        }
      }
    },
    {
      "text": "Desktop cloud login switches owned data. The Cloud Account’s credentials are exchanged for a 登录设备 token. A different account switches the native client to that account’s own local book, without writing to the previous one; the same account enters as the book’s local administrator.",
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
          "entity": "logged-device",
          "effect": "creates",
          "facts": [
            "Name",
            "Platform",
            "Architecture",
            "Client version",
            "Login time",
            "Last use",
            "Revocation"
          ],
          "to": "Active"
        },
        {
          "entity": "desktop-config",
          "effect": "changes",
          "facts": [
            "Account binding",
            "Data location",
            "Remembered route"
          ]
        }
      ],
      "actor": "crm-sales",
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

# Desktop cloud login switches owned data

## Trigger

A CRM member invokes sign in for the case “Desktop cloud login switches owned data”.

## Outcome

Desktop cloud login switches owned data. The Cloud Account’s credentials are exchanged for a 登录设备 token. A different account switches the native client to that account’s own local book, without writing to the previous one; the same account enters as the book’s local administrator.
