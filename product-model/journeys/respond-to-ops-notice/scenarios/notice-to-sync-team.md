---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "do": "DO"
  },
  "steps": [
    {
      "text": "Activate the native pending-team notice.",
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
      "text": "The native pending-team notice carries the safe team subject to the console.",
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
      "text": "Inspect the sync-team queue carried into the web console.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "do": {
          "place": "crm-web::operations::sync-teams"
        }
      },
      "capability": "browse-sync-teams"
    },
    {
      "text": "The console opens synchronization-team inspection. Activation remains a separate operation, with its own operator decision.",
      "kind": "product",
      "entities": [
        {
          "entity": "sync-team",
          "effect": "reads",
          "facts": [
            "Name",
            "Active",
            "Activation time",
            "Invite/key generation",
            "Creator",
            "Sync state"
          ]
        }
      ],
      "actor": "operator",
      "contexts": {
        "do": {
          "place": "crm-web::operations::sync-teams"
        }
      },
      "capability": "browse-sync-teams"
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
      "target": "src/app/admin/sync/page.tsx"
    }
  ]
}
---

# Notice To Sync Team

## Trigger

The native pending-team notice carries the safe team subject to the console.

## Outcome

The console opens synchronization-team inspection. Activation remains a separate operation, with its own operator decision.
