---
{
  "kind": "edge",
  "routes": {
    "wo": "Web operations"
  },
  "steps": [
    {
      "text": "The operator invokes browse model usage for the case “Unconfigured pricing/no usage records”.",
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
      "text": "Without configured token pricing, operations displays token usage without a fabricated monetary estimate. No retained calls produce an empty usage result; missing provider usage or best-effort logging is not reconstructed as zero-cost calls.",
      "kind": "product",
      "entities": [],
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

# Unconfigured pricing/no usage records

## Trigger

The operator invokes browse model usage for the case “Unconfigured pricing/no usage records”.

## Outcome

Without configured token pricing, operations displays token usage without a fabricated monetary estimate. No retained calls produce an empty usage result; missing provider usage or best-effort logging is not reconstructed as zero-cost calls.
