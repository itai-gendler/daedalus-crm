---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "do": "DO"
  },
  "steps": [
    {
      "text": "Activate the native registration or account-usage notice.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "do": {
          "place": "crm-desktop::operations"
        }
      },
      "capability": "receive-ops-notices"
    },
    {
      "text": "The native registration notice carries a safe account subject or grouped account list to the console.",
      "kind": "product",
      "entities": [
        {
          "entity": "desktop-config",
          "effect": "reads",
          "facts": [
            "Operations cursor"
          ]
        }
      ],
      "actor": "operator",
      "contexts": {
        "do": {
          "place": "crm-desktop::operations"
        }
      },
      "capability": "receive-ops-notices"
    },
    {
      "text": "Inspect its selected account detail or the grouped account list in the console.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "do": {
          "place": "crm-web::operations::accounts"
        }
      },
      "capability": "browse-cloud-accounts"
    },
    {
      "text": "The console opens the safe account destination carried by the notice. A grouped registration notice opens the account list; a single account notice retains its subject identifier.",
      "kind": "product",
      "entities": [
        {
          "entity": "cloud-account",
          "effect": "reads",
          "facts": [
            "Name",
            "Contact",
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
        "do": {
          "place": "crm-web::operations::accounts"
        }
      },
      "capability": "browse-cloud-accounts"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/ops-notices.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "desktop/main.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/ops-notices.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/admin/data.ts"
    }
  ]
}
---

# Notice To Account

## Trigger

The native registration notice carries a safe account subject or grouped account list to the console.

## Outcome

The console opens the safe account destination carried by the notice. A grouped registration notice opens the account list; a single account notice retains its subject identifier.
