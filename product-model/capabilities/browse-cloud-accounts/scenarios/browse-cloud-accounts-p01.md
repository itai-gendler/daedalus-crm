---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator requests the account list or selected account detail.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::accounts"
        }
      }
    },
    {
      "text": "Account list/detail/devices/gifts. Lists at most 500 accounts and inspects a selected account, devices and gift history.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "reads",
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
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::accounts"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/data.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/guard.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ops-auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/ops-notices.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/feedback-reply.ts"
    }
  ]
}
---

# Account list/detail/devices/gifts

## Trigger

The operator requests the account list or selected account detail.

## Outcome

Account list/detail/devices/gifts. Lists at most 500 accounts and inspects a selected account, devices and gift history.
