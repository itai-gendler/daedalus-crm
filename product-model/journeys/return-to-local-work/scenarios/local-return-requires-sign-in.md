---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "da": "DA"
  },
  "steps": [
    {
      "text": "Invoke return to local data when the book has no valid local session.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::public::server-connection"
        }
      },
      "capability": "change-desktop-settings"
    },
    {
      "text": "Return-local starts the owned book but missing local session carries the known role holder into native login.",
      "kind": "product",
      "entities": [
        {
          "entity": "desktop-config",
          "effect": "changes",
          "facts": [
            "Data mode"
          ],
          "from": "Server",
          "to": "Local"
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::public::server-connection"
        }
      },
      "capability": "change-desktop-settings"
    },
    {
      "text": "Enter the cloud credentials in native login and complete the account-owned local sign-in.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::public::login-or-registration"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "Retained mode becomes Local. Native login recognizes the cloud account, creates its logged device and selects only that account's local data binding. Successful sign-in continues through the local session landing; rejected identity never adopts another account's files.",
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
        "da": {
          "place": "crm-desktop::public::login-or-registration"
        }
      },
      "capability": "sign-in"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/main.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/login/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/login/after-login.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/landing.ts"
    }
  ]
}
---

# Local Return Requires Sign In

## Trigger

Return-local starts the owned book but missing local session carries the known role holder into native login.

## Outcome

Retained mode becomes Local. Native login recognizes the cloud account, creates its logged device and selects only that account's local data binding. Successful sign-in continues through the local session landing; rejected identity never adopts another account's files.
