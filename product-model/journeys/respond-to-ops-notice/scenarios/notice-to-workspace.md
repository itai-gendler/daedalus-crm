---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "do": "DO"
  },
  "steps": [
    {
      "text": "Activate the native workspace-usage notice.",
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
      "text": "The native workspace notice carries the safe workspace subject to the console.",
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
      "text": "Inspect the workspace list carried into the console.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "do": {
          "place": "crm-web::operations::workspaces"
        }
      },
      "capability": "browse-workspaces"
    },
    {
      "text": "The console opens the workspace destination carried by the notice; inspection leaves subscription and activation settings unchanged.",
      "kind": "product",
      "entities": [
        {
          "entity": "workspace",
          "effect": "reads",
          "facts": [
            "Name",
            "Address/slug",
            "Status",
            "Trial expiry",
            "Paid expiry",
            "Plan",
            "AI allowance",
            "Notes",
            "Payment references"
          ]
        }
      ],
      "actor": "operator",
      "contexts": {
        "do": {
          "place": "crm-web::operations::workspaces"
        }
      },
      "capability": "browse-workspaces"
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
      "target": "src/app/admin/workspaces/page.tsx"
    }
  ]
}
---

# Notice To Workspace

## Trigger

The native workspace notice carries the safe workspace subject to the console.

## Outcome

The console opens the workspace destination carried by the notice; inspection leaves subscription and activation settings unchanged.
