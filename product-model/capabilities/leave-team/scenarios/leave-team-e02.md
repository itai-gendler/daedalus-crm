---
{
  "kind": "edge",
  "routes": {
    "da": "Native CRM"
  },
  "steps": [
    {
      "text": "A CRM member invokes leave team for the case “Unknown identity is not pruned”.",
      "kind": "actor",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    },
    {
      "text": "Offline or already removed local exit is possible; unknown identity does not trigger the known noncreator data-pruning path.",
      "kind": "product",
      "entities": [],
      "actor": "crm-sales",
      "contexts": {
        "da": {
          "place": "crm-desktop::crm::team"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/team-actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/(app)/settings/TeamTab.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/client.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/local.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/sync/tables.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/sync-relay.ts"
    }
  ]
}
---

# Unknown identity is not pruned

## Trigger

A CRM member invokes leave team for the case “Unknown identity is not pruned”.

## Outcome

Offline or already removed local exit is possible; unknown identity does not trigger the known noncreator data-pruning path.
