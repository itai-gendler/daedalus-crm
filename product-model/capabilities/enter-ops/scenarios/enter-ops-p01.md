---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes enter ops for the case “URL token entry”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations"
        }
      }
    },
    {
      "text": "URL token entry. The hosted console validates the configured console token or active operator account. Native entry exchanges a one-use 60-second code and the console session lasts 12 hours.",
      "kind": "product",
      "entities": [
        {
          "entity": "service-config",
          "effect": "reads",
          "facts": [
            "Hosting/native mode",
            "Operator identities",
            "Console credential"
          ]
        }
      ],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations"
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

# URL token entry

## Trigger

The operator invokes enter ops for the case “URL token entry”.

## Outcome

URL token entry. The hosted console validates the configured console token or active operator account. Native entry exchanges a one-use 60-second code and the console session lasts 12 hours.
