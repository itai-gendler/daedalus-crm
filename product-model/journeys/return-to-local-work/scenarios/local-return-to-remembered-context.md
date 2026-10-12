---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "da": "DA"
  },
  "steps": [
    {
      "text": "Invoke return to local data from the chosen server context.",
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
      "text": "Return-local starts the owned book and its valid session landing carries the remembered record route.",
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
      "text": "Inspect the customer record reached by the valid local session and remembered route.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      },
      "capability": "browse-customers"
    },
    {
      "text": "Retained mode becomes Local and the account-owned book resumes its accepted remembered route. Route validity does not prove that customer still exists; its missing result remains visible.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Name",
            "Phone",
            "WhatsApp",
            "WeChat",
            "Country",
            "Email",
            "School/company",
            "Grade",
            "Major",
            "Follow-up status",
            "Decision status",
            "Expected signing date",
            "Sales owner",
            "Direct source",
            "Direct channel",
            "Referrer",
            "Attributed channel",
            "Attributed customer",
            "Channel owner",
            "Notes",
            "Latest follow-up",
            "Pool state",
            "Pool entry",
            "Released by",
            "Claim time",
            "Claimed by",
            "Created time",
            "Last change"
          ]
        }
      ],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::customer-record"
        }
      },
      "capability": "browse-customers"
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
      "target": "desktop/route-memory.js"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/desktop/landing.ts"
    }
  ]
}
---

# Local Return To Remembered Context

## Trigger

Return-local starts the owned book and its valid session landing carries the remembered record route.

## Outcome

Retained mode becomes Local and the account-owned book resumes its accepted remembered route. Route validity does not prove that customer still exists; its missing result remains visible.
