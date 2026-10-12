---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes sign out for the case “Desktop revokes current device and retains data”.",
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
      "text": "Desktop revokes current device and retains data. Web clears its session; native exit revokes the current device where cloud is reachable, clears the local session and retains local files.",
      "kind": "product",
      "entities": [
        {
          "entity": "logged-device",
          "effect": "changes",
          "facts": [
            "Revocation"
          ]
        }
      ],
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

# Desktop revokes current device and retains data

## Trigger

A CRM member invokes sign out for the case “Desktop revokes current device and retains data”.

## Outcome

Desktop revokes current device and retains data. Web clears its session; native exit revokes the current device where cloud is reachable, clears the local session and retains local files.
