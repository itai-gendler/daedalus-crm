---
{
  "kind": "edge",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes sign out for the case “Local exit while cloud unavailable”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::profile"
        },
        "da": {
          "place": "crm-desktop::crm::profile"
        }
      }
    },
    {
      "text": "Native local session ends and files remain even when cloud revocation cannot finish.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "wa": {
          "place": "crm-web::crm::profile"
        },
        "da": {
          "place": "crm-desktop::crm::profile"
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

# Local exit while cloud unavailable

## Trigger

A CRM member invokes sign out for the case “Local exit while cloud unavailable”.

## Outcome

Native local session ends and files remain even when cloud revocation cannot finish.
