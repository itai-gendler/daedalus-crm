---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "do": "DO"
  },
  "steps": [
    {
      "text": "Activate the native feedback notice.",
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
      "text": "The native feedback notice carries the safe feedback queue/subject to the console.",
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
      "text": "Inspect the feedback queue carried into the web console.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "do": {
          "place": "crm-web::operations::feedback"
        }
      },
      "capability": "browse-feedback"
    },
    {
      "text": "The console opens the actual feedback queue destination; the notice does not create or handle feedback by itself.",
      "kind": "product",
      "entities": [
        {
          "entity": "feedback",
          "effect": "reads",
          "facts": [
            "Body",
            "Page",
            "Version",
            "System",
            "Account/contact",
            "Submitted time",
            "Handled",
            "Replies"
          ]
        }
      ],
      "actor": "operator",
      "contexts": {
        "do": {
          "place": "crm-web::operations::feedback"
        }
      },
      "capability": "browse-feedback"
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
      "target": "src/app/admin/feedback/page.tsx"
    }
  ]
}
---

# Notice To Feedback

## Trigger

The native feedback notice carries the safe feedback queue/subject to the console.

## Outcome

The console opens the actual feedback queue destination; the notice does not create or handle feedback by itself.
