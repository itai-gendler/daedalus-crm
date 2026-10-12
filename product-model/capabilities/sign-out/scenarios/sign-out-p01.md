---
{
  "kind": "primary",
  "routes": {
    "wa": "Web CRM",
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes sign out for the case “Web clears session”.",
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
      "text": "Web clears session. Web clears its session; native exit revokes the current device where cloud is reachable, clears the local session and retains local files.",
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

# Web clears session

## Trigger

A CRM member invokes sign out for the case “Web clears session”.

## Outcome

Web clears session. Web clears its session; native exit revokes the current device where cloud is reachable, clears the local session and retains local files.
