---
{
  "kind": "primary",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes browse model usage for the case “30-day call/feature/model/attribution”.",
      "kind": "actor",
      "entities": [],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::model-usage"
        }
      }
    },
    {
      "text": "30-day call/feature/model/attribution. Shows 30-day call/feature/model/owner attribution. Costs require configured prices and actual recorded usage; missing usage is not zero.",
      "kind": "product",
      "entities": [
        {
          "entity": "model-usage-log",
          "effect": "reads",
          "facts": [
            "Time",
            "Owner attribution",
            "Feature",
            "Model",
            "Input usage",
            "Output usage"
          ]
        }
      ],
      "actor": "operator",
      "contexts": {
        "wo": {
          "place": "crm-web::operations::model-usage"
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

# 30-day call/feature/model/attribution

## Trigger

The operator invokes browse model usage for the case “30-day call/feature/model/attribution”.

## Outcome

30-day call/feature/model/attribution. Shows 30-day call/feature/model/owner attribution. Costs require configured prices and actual recorded usage; missing usage is not zero.
