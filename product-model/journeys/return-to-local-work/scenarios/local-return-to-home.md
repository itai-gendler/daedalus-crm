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
      "text": "Return-local starts the owned book and its valid session landing carries the default home.",
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
      "text": "Read the default local home reached by the valid session.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::home"
        }
      },
      "capability": "browse-data"
    },
    {
      "text": "Retained mode becomes Local and the same account-owned book opens its default home instead of reusing the remote site's remembered path.",
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
          "place": "crm-desktop::crm::home"
        }
      },
      "capability": "browse-data"
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

# Local Return To Home

## Trigger

Return-local starts the owned book and its valid session landing carries the default home.

## Outcome

Retained mode becomes Local and the same account-owned book opens its default home instead of reusing the remote site's remembered path.
